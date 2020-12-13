---
ms.date: 09/13/2016
ms.topic: reference
title: WideControl の EntrySelectedBy の SelectionCondition の TypeName 要素 (書式)
description: WideControl の EntrySelectedBy の SelectionCondition の TypeName 要素 (書式)
ms.openlocfilehash: af6e4782c345b43e16bce59c333bdaaceba0d845
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645513"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="f5a26-103">WideControl の EntrySelectedBy の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f5a26-103">TypeName Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="f5a26-104">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5a26-104">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="f5a26-105">この型が存在する場合は、定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5a26-105">When this type is present, the definition is used.</span></span>

<span data-ttu-id="f5a26-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideEntry (format) の SelectionCondition 要素に対して、EntrySelectedBy for WideEntry (format) の SelectionCondition 要素を指定します。 entryselectedby for WideEntry (Format) の SelectionCondition を使用します。</span><span class="sxs-lookup"><span data-stu-id="f5a26-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f5a26-107">構文</span><span class="sxs-lookup"><span data-stu-id="f5a26-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f5a26-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f5a26-108">Attributes and Elements</span></span>

<span data-ttu-id="f5a26-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。</span><span class="sxs-lookup"><span data-stu-id="f5a26-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f5a26-110">属性</span><span class="sxs-lookup"><span data-stu-id="f5a26-110">Attributes</span></span>

<span data-ttu-id="f5a26-111">なし。</span><span class="sxs-lookup"><span data-stu-id="f5a26-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f5a26-112">子要素</span><span class="sxs-lookup"><span data-stu-id="f5a26-112">Child Elements</span></span>

<span data-ttu-id="f5a26-113">なし。</span><span class="sxs-lookup"><span data-stu-id="f5a26-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f5a26-114">親要素</span><span class="sxs-lookup"><span data-stu-id="f5a26-114">Parent Elements</span></span>

|<span data-ttu-id="f5a26-115">要素</span><span class="sxs-lookup"><span data-stu-id="f5a26-115">Element</span></span>|<span data-ttu-id="f5a26-116">説明</span><span class="sxs-lookup"><span data-stu-id="f5a26-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f5a26-117">WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="f5a26-117">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="f5a26-118">このワイドエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="f5a26-118">Defines the condition that must exist for this wide entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f5a26-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="f5a26-119">Text Value</span></span>

<span data-ttu-id="f5a26-120">.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="f5a26-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f5a26-121">解説</span><span class="sxs-lookup"><span data-stu-id="f5a26-121">Remarks</span></span>

<span data-ttu-id="f5a26-122">選択条件では、.NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="f5a26-122">The selection condition can specify a .NET type or a selection set, but cannot specify both.</span></span> <span data-ttu-id="f5a26-123">選択条件の使用方法の詳細については、「 [データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5a26-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="f5a26-124">ワイドビューのその他のコンポーネントの詳細については、「 [ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5a26-124">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f5a26-125">参照</span><span class="sxs-lookup"><span data-stu-id="f5a26-125">See Also</span></span>

[<span data-ttu-id="f5a26-126">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="f5a26-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="f5a26-127">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="f5a26-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="f5a26-128">WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="f5a26-128">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="f5a26-129">WideEntry の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f5a26-129">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="f5a26-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="f5a26-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
