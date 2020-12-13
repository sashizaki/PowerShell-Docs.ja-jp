---
ms.date: 09/13/2016
ms.topic: reference
title: View の CustomControl の EntrySelectedBy の SelectionSetName 要素 (書式)
description: View の CustomControl の EntrySelectedBy の SelectionSetName 要素 (書式)
ms.openlocfilehash: a158c5476fb3a168a146ce67565c0ed6f7859519
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651924"
---
# <a name="selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format"></a><span data-ttu-id="80247-103">View の CustomControl の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="80247-103">SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)</span></span>

<span data-ttu-id="80247-104">リストエントリの一連の .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="80247-104">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="80247-105">エントリに指定できる選択セットの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="80247-105">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="80247-106">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (Format) CustomControl 要素 (形式) の CustomEntries for CustomControl for view (format) SelectionSetName Element for customentry for の EntrySelectedBy 要素を使用して、customentry 用の entryselectedby の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="80247-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="80247-107">構文</span><span class="sxs-lookup"><span data-stu-id="80247-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="80247-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="80247-108">Attributes and Elements</span></span>

<span data-ttu-id="80247-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="80247-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="80247-110">属性</span><span class="sxs-lookup"><span data-stu-id="80247-110">Attributes</span></span>

<span data-ttu-id="80247-111">なし。</span><span class="sxs-lookup"><span data-stu-id="80247-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="80247-112">子要素</span><span class="sxs-lookup"><span data-stu-id="80247-112">Child Elements</span></span>

<span data-ttu-id="80247-113">なし。</span><span class="sxs-lookup"><span data-stu-id="80247-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="80247-114">親要素</span><span class="sxs-lookup"><span data-stu-id="80247-114">Parent Elements</span></span>

|<span data-ttu-id="80247-115">要素</span><span class="sxs-lookup"><span data-stu-id="80247-115">Element</span></span>|<span data-ttu-id="80247-116">説明</span><span class="sxs-lookup"><span data-stu-id="80247-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="80247-117">CustomEntry for ビューの EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="80247-117">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="80247-118">このカスタムエントリを使用する .NET 型、またはこのエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="80247-118">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="80247-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="80247-119">Text Value</span></span>

<span data-ttu-id="80247-120">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="80247-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="80247-121">解説</span><span class="sxs-lookup"><span data-stu-id="80247-121">Remarks</span></span>

<span data-ttu-id="80247-122">各カスタムコントロールエントリには、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="80247-122">Each custom control entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="80247-123">選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="80247-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="80247-124">たとえば、同じオブジェクトのセットに対してテーブルビューとリストビューを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="80247-124">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="80247-125">選択セットの定義の詳細については、「 [選択セットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80247-125">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="80247-126">カスタムコントロールビューのコンポーネントの詳細については、「 [カスタムコントロールの作成](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80247-126">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="80247-127">参照</span><span class="sxs-lookup"><span data-stu-id="80247-127">See Also</span></span>

[<span data-ttu-id="80247-128">CustomEntry for ビューの EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="80247-128">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="80247-129">カスタムコントロールビュー</span><span class="sxs-lookup"><span data-stu-id="80247-129">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="80247-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="80247-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
