---
ms.date: 09/13/2016
ms.topic: reference
title: GroupBy の EntrySelectedBy の SelectionSetName 要素 (書式)
description: GroupBy の EntrySelectedBy の SelectionSetName 要素 (書式)
ms.openlocfilehash: 7ebe5d884061243c8b4af196788187d84c15a92e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651846"
---
# <a name="selectionsetname-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="dfe18-103">GroupBy の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="dfe18-103">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="dfe18-104">リストエントリの一連の .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="dfe18-104">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="dfe18-105">エントリに指定できる選択セットの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="dfe18-105">There is no limit to the number of selection sets that can be specified for an entry.</span></span> <span data-ttu-id="dfe18-106">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="dfe18-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="dfe18-107">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の GroupBy 要素を使用して、groupby (形式) の CustomControl 要素に対して groupby (format) CustomEntries 要素の CustomControl の CustomControl for groupby (形式) の CustomEntry 要素を使用して、groupby (形式) の EntrySelectedBy の SelectionSetName 要素。</span><span class="sxs-lookup"><span data-stu-id="dfe18-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="dfe18-108">構文</span><span class="sxs-lookup"><span data-stu-id="dfe18-108">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="dfe18-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="dfe18-109">Attributes and Elements</span></span>

<span data-ttu-id="dfe18-110">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="dfe18-110">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="dfe18-111">属性</span><span class="sxs-lookup"><span data-stu-id="dfe18-111">Attributes</span></span>

<span data-ttu-id="dfe18-112">なし。</span><span class="sxs-lookup"><span data-stu-id="dfe18-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="dfe18-113">子要素</span><span class="sxs-lookup"><span data-stu-id="dfe18-113">Child Elements</span></span>

<span data-ttu-id="dfe18-114">なし。</span><span class="sxs-lookup"><span data-stu-id="dfe18-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="dfe18-115">親要素</span><span class="sxs-lookup"><span data-stu-id="dfe18-115">Parent Elements</span></span>

|<span data-ttu-id="dfe18-116">要素</span><span class="sxs-lookup"><span data-stu-id="dfe18-116">Element</span></span>|<span data-ttu-id="dfe18-117">説明</span><span class="sxs-lookup"><span data-stu-id="dfe18-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dfe18-118">GroupBy の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="dfe18-118">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="dfe18-119">このカスタムエントリを使用する .NET 型、またはこのエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="dfe18-119">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="dfe18-120">テキスト値</span><span class="sxs-lookup"><span data-stu-id="dfe18-120">Text Value</span></span>

<span data-ttu-id="dfe18-121">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="dfe18-121">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="dfe18-122">解説</span><span class="sxs-lookup"><span data-stu-id="dfe18-122">Remarks</span></span>

<span data-ttu-id="dfe18-123">各カスタムコントロール定義には、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe18-123">Each custom control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="dfe18-124">選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="dfe18-124">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="dfe18-125">たとえば、同じオブジェクトのセットに対してテーブルビューとリストビューを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="dfe18-125">For example, you may want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="dfe18-126">選択セットの定義の詳細については、「 [選択セットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfe18-126">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="dfe18-127">カスタムコントロールビューのコンポーネントの詳細については、「 [カスタムコントロールの作成](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfe18-127">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dfe18-128">参照</span><span class="sxs-lookup"><span data-stu-id="dfe18-128">See Also</span></span>

[<span data-ttu-id="dfe18-129">GroupBy の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="dfe18-129">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="dfe18-130">カスタム コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="dfe18-130">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="dfe18-131">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="dfe18-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
