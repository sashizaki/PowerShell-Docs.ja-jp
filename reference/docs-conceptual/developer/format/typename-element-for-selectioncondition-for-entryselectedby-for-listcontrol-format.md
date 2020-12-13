---
ms.date: 09/13/2016
ms.topic: reference
title: ListControl の EntrySelectedBy の SelectionCondition の TypeName 要素 (書式)
description: ListControl の EntrySelectedBy の SelectionCondition の TypeName 要素 (書式)
ms.openlocfilehash: 2e8246e3ef2cba38824d8f8004acfffc3236df13
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645557"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="d6f8c-103">ListControl の EntrySelectedBy の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d6f8c-103">TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="d6f8c-104">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6f8c-104">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="d6f8c-105">この型が存在する場合は、リストエントリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d6f8c-105">When this type is present, the list entry is used.</span></span>

<span data-ttu-id="d6f8c-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) ListControl Element (format) ListEntries for ListControl (format) ListEntry 要素の ListEntries for ListControl (format) 要素の Listselectedby for ListEntry (format) の SelectionCondition for ListControl (format) の selectioncondition の selectioncondition for ListControl (format) の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="d6f8c-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format) SelectionCondition Element for EntrySelectedBy for ListControl (Format) TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d6f8c-107">構文</span><span class="sxs-lookup"><span data-stu-id="d6f8c-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d6f8c-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d6f8c-108">Attributes and Elements</span></span>

<span data-ttu-id="d6f8c-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。</span><span class="sxs-lookup"><span data-stu-id="d6f8c-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d6f8c-110">属性</span><span class="sxs-lookup"><span data-stu-id="d6f8c-110">Attributes</span></span>

<span data-ttu-id="d6f8c-111">なし。</span><span class="sxs-lookup"><span data-stu-id="d6f8c-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d6f8c-112">子要素</span><span class="sxs-lookup"><span data-stu-id="d6f8c-112">Child Elements</span></span>

<span data-ttu-id="d6f8c-113">なし。</span><span class="sxs-lookup"><span data-stu-id="d6f8c-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d6f8c-114">親要素</span><span class="sxs-lookup"><span data-stu-id="d6f8c-114">Parent Elements</span></span>

|<span data-ttu-id="d6f8c-115">要素</span><span class="sxs-lookup"><span data-stu-id="d6f8c-115">Element</span></span>|<span data-ttu-id="d6f8c-116">説明</span><span class="sxs-lookup"><span data-stu-id="d6f8c-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d6f8c-117">ListControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d6f8c-117">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="d6f8c-118">このリストエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="d6f8c-118">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d6f8c-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="d6f8c-119">Text Value</span></span>

<span data-ttu-id="d6f8c-120">.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="d6f8c-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d6f8c-121">解説</span><span class="sxs-lookup"><span data-stu-id="d6f8c-121">Remarks</span></span>

<span data-ttu-id="d6f8c-122">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d6f8c-122">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="d6f8c-123">選択条件の使用方法の詳細については、「 [データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6f8c-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="d6f8c-124">リストビューのその他のコンポーネントの詳細については、「 [リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6f8c-124">For more information about other the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d6f8c-125">参照</span><span class="sxs-lookup"><span data-stu-id="d6f8c-125">See Also</span></span>

[<span data-ttu-id="d6f8c-126">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="d6f8c-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="d6f8c-127">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="d6f8c-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="d6f8c-128">ListControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d6f8c-128">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="d6f8c-129">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="d6f8c-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
