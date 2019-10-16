---
title: ListControl (Format) の EntrySelectedBy の SelectionCondition の TypeName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd025a3a-3780-40db-a068-873e7df38015
caps.latest.revision: 9
ms.openlocfilehash: 2b76b040b39088cc9c3b9d6890c38df3c533b39f
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361561"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="38c4a-102">ListControl の EntrySelectedBy の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="38c4a-102">TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="38c4a-103">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="38c4a-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="38c4a-104">この型が存在する場合は、リストエントリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="38c4a-104">When this type is present, the list entry is used.</span></span>

<span data-ttu-id="38c4a-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) ListControl 要素 (Format) ListEntry 要素の ListControl (format) 要素の listentries 要素の listentries to ElementListControl (Format) の EntrySelectedBy の ListControl (Format) TypeName 要素の EntrySelectedBy の ListEntry for ListControl (format) SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="38c4a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format) SelectionCondition Element for EntrySelectedBy for ListControl (Format) TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="38c4a-106">構文</span><span class="sxs-lookup"><span data-stu-id="38c4a-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="38c4a-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="38c4a-107">Attributes and Elements</span></span>

<span data-ttu-id="38c4a-108">次のセクションでは、属性、子要素、`TypeName` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="38c4a-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="38c4a-109">属性</span><span class="sxs-lookup"><span data-stu-id="38c4a-109">Attributes</span></span>

<span data-ttu-id="38c4a-110">なし。</span><span class="sxs-lookup"><span data-stu-id="38c4a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="38c4a-111">子要素</span><span class="sxs-lookup"><span data-stu-id="38c4a-111">Child Elements</span></span>

<span data-ttu-id="38c4a-112">なし。</span><span class="sxs-lookup"><span data-stu-id="38c4a-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="38c4a-113">親要素</span><span class="sxs-lookup"><span data-stu-id="38c4a-113">Parent Elements</span></span>

|<span data-ttu-id="38c4a-114">要素</span><span class="sxs-lookup"><span data-stu-id="38c4a-114">Element</span></span>|<span data-ttu-id="38c4a-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="38c4a-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="38c4a-116">ListControl (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="38c4a-116">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="38c4a-117">このリストエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="38c4a-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="38c4a-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="38c4a-118">Text Value</span></span>

<span data-ttu-id="38c4a-119">.NET 型の完全修飾名 (`System.IO.DirectoryInfo` など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="38c4a-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="38c4a-120">コメント</span><span class="sxs-lookup"><span data-stu-id="38c4a-120">Remarks</span></span>

<span data-ttu-id="38c4a-121">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="38c4a-121">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="38c4a-122">選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38c4a-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="38c4a-123">リストビューのその他のコンポーネントの詳細については、「[リストビューの作成](./creating-a-list-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38c4a-123">For more information about other the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="38c4a-124">参照</span><span class="sxs-lookup"><span data-stu-id="38c4a-124">See Also</span></span>

[<span data-ttu-id="38c4a-125">リストビューの作成</span><span class="sxs-lookup"><span data-stu-id="38c4a-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="38c4a-126">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="38c4a-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="38c4a-127">ListControl (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="38c4a-127">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="38c4a-128">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="38c4a-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
