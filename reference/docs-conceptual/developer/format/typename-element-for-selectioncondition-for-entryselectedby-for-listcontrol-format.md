---
title: ListControl (Format) の EntrySelectedBy の SelectionCondition の TypeName 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: bc58d630e65b316f9223bf3c529f928358e38ebc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787377"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="8a344-102">ListControl の EntrySelectedBy の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8a344-102">TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="8a344-103">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="8a344-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="8a344-104">この型が存在する場合は、リストエントリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="8a344-104">When this type is present, the list entry is used.</span></span>

<span data-ttu-id="8a344-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) ListControl Element (format) ListEntries for ListControl (format) ListEntry 要素の ListEntries for ListControl (format) 要素の Listselectedby for ListEntry (format) の SelectionCondition for ListControl (format) の selectioncondition の selectioncondition for ListControl (format) の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="8a344-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format) SelectionCondition Element for EntrySelectedBy for ListControl (Format) TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8a344-106">構文</span><span class="sxs-lookup"><span data-stu-id="8a344-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8a344-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8a344-107">Attributes and Elements</span></span>

<span data-ttu-id="8a344-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。</span><span class="sxs-lookup"><span data-stu-id="8a344-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8a344-109">属性</span><span class="sxs-lookup"><span data-stu-id="8a344-109">Attributes</span></span>

<span data-ttu-id="8a344-110">なし。</span><span class="sxs-lookup"><span data-stu-id="8a344-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8a344-111">子要素</span><span class="sxs-lookup"><span data-stu-id="8a344-111">Child Elements</span></span>

<span data-ttu-id="8a344-112">なし。</span><span class="sxs-lookup"><span data-stu-id="8a344-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8a344-113">親要素</span><span class="sxs-lookup"><span data-stu-id="8a344-113">Parent Elements</span></span>

|<span data-ttu-id="8a344-114">要素</span><span class="sxs-lookup"><span data-stu-id="8a344-114">Element</span></span>|<span data-ttu-id="8a344-115">説明</span><span class="sxs-lookup"><span data-stu-id="8a344-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8a344-116">ListControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8a344-116">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="8a344-117">このリストエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="8a344-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8a344-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="8a344-118">Text Value</span></span>

<span data-ttu-id="8a344-119">.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="8a344-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="8a344-120">解説</span><span class="sxs-lookup"><span data-stu-id="8a344-120">Remarks</span></span>

<span data-ttu-id="8a344-121">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="8a344-121">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="8a344-122">選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a344-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="8a344-123">リストビューのその他のコンポーネントの詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a344-123">For more information about other the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8a344-124">参照</span><span class="sxs-lookup"><span data-stu-id="8a344-124">See Also</span></span>

[<span data-ttu-id="8a344-125">リスト ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="8a344-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="8a344-126">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="8a344-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="8a344-127">ListControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8a344-127">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="8a344-128">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="8a344-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
