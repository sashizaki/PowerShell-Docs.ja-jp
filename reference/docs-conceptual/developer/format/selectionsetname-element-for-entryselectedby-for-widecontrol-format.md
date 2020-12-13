---
ms.date: 09/13/2016
ms.topic: reference
title: WideControl の EntrySelectedBy の SelectionSetName 要素 (書式)
description: WideControl の EntrySelectedBy の SelectionSetName 要素 (書式)
ms.openlocfilehash: bf6a44bb733421f36a9140d0ec10e61aedfbda6a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651698"
---
# <a name="selectionsetname-element-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="2f6dc-103">WideControl の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2f6dc-103">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="2f6dc-104">定義の .NET オブジェクトのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="2f6dc-104">Specifies a set of .NET objects for the definition.</span></span> <span data-ttu-id="2f6dc-105">これらのオブジェクトのいずれかが表示されるたびに、定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2f6dc-105">The definition is used whenever one of these objects is displayed.</span></span>

<span data-ttu-id="2f6dc-106">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (Format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) WideEntry (Format) SelectionSetName Element for WideEntry (format) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="2f6dc-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2f6dc-107">構文</span><span class="sxs-lookup"><span data-stu-id="2f6dc-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="2f6dc-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2f6dc-108">Attributes and Elements</span></span>

<span data-ttu-id="2f6dc-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="2f6dc-109">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2f6dc-110">属性</span><span class="sxs-lookup"><span data-stu-id="2f6dc-110">Attributes</span></span>

<span data-ttu-id="2f6dc-111">なし。</span><span class="sxs-lookup"><span data-stu-id="2f6dc-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2f6dc-112">子要素</span><span class="sxs-lookup"><span data-stu-id="2f6dc-112">Child Elements</span></span>

<span data-ttu-id="2f6dc-113">なし。</span><span class="sxs-lookup"><span data-stu-id="2f6dc-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2f6dc-114">親要素</span><span class="sxs-lookup"><span data-stu-id="2f6dc-114">Parent Elements</span></span>

|<span data-ttu-id="2f6dc-115">要素</span><span class="sxs-lookup"><span data-stu-id="2f6dc-115">Element</span></span>|<span data-ttu-id="2f6dc-116">説明</span><span class="sxs-lookup"><span data-stu-id="2f6dc-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2f6dc-117">WideEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2f6dc-117">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="2f6dc-118">このワイドエントリを使用する .NET 型、またはこのエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="2f6dc-118">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2f6dc-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="2f6dc-119">Text Value</span></span>

<span data-ttu-id="2f6dc-120">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2f6dc-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="2f6dc-121">解説</span><span class="sxs-lookup"><span data-stu-id="2f6dc-121">Remarks</span></span>

<span data-ttu-id="2f6dc-122">各定義には、1つの型名、選択セット、または選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f6dc-122">Each definition must specify one type name, selection set, or selection condition.</span></span>

<span data-ttu-id="2f6dc-123">選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="2f6dc-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="2f6dc-124">たとえば、同じオブジェクトのセットに対してテーブルビューとリストビューを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="2f6dc-124">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="2f6dc-125">選択セットの定義の詳細については、「 [ビューのオブジェクトセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f6dc-125">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="2f6dc-126">ワイドビューのその他のコンポーネントの詳細については、「 [ワイドビューの作成](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f6dc-126">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2f6dc-127">参照</span><span class="sxs-lookup"><span data-stu-id="2f6dc-127">See Also</span></span>

[<span data-ttu-id="2f6dc-128">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="2f6dc-128">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="2f6dc-129">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="2f6dc-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="2f6dc-130">WideEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2f6dc-130">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="2f6dc-131">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="2f6dc-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
