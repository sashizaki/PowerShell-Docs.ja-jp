---
title: GroupBy (Format) の EntrySelectedBy の SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d569c623-2277-49e3-933e-c26262b91cd5
caps.latest.revision: 6
ms.openlocfilehash: 69cd113c444b4e3c5dceabcdfddb439cd1376f6b
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364741"
---
# <a name="selectionsetname-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="1e853-102">GroupBy の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1e853-102">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="1e853-103">リストエントリの一連の .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="1e853-103">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="1e853-104">エントリに指定できる選択セットの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="1e853-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span> <span data-ttu-id="1e853-105">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="1e853-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="1e853-106">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素の groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素Groupby (format) の CustomControl に対して、CustomEntry for groupby (format) の SelectionSetName 要素を指定します。 groupby (形式) に対して EntrySelectedBy の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="1e853-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1e853-107">構文</span><span class="sxs-lookup"><span data-stu-id="1e853-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1e853-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="1e853-108">Attributes and Elements</span></span>

<span data-ttu-id="1e853-109">次のセクションでは、`SelectionSetName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1e853-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1e853-110">属性</span><span class="sxs-lookup"><span data-stu-id="1e853-110">Attributes</span></span>

<span data-ttu-id="1e853-111">なし。</span><span class="sxs-lookup"><span data-stu-id="1e853-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1e853-112">子要素</span><span class="sxs-lookup"><span data-stu-id="1e853-112">Child Elements</span></span>

<span data-ttu-id="1e853-113">なし。</span><span class="sxs-lookup"><span data-stu-id="1e853-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1e853-114">親要素</span><span class="sxs-lookup"><span data-stu-id="1e853-114">Parent Elements</span></span>

|<span data-ttu-id="1e853-115">要素</span><span class="sxs-lookup"><span data-stu-id="1e853-115">Element</span></span>|<span data-ttu-id="1e853-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="1e853-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1e853-117">GroupBy の CustomEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="1e853-117">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="1e853-118">このカスタムエントリを使用する .NET 型、またはこのエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="1e853-118">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1e853-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="1e853-119">Text Value</span></span>

<span data-ttu-id="1e853-120">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1e853-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="1e853-121">コメント</span><span class="sxs-lookup"><span data-stu-id="1e853-121">Remarks</span></span>

<span data-ttu-id="1e853-122">各カスタムコントロール定義には、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e853-122">Each custom control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="1e853-123">選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="1e853-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="1e853-124">たとえば、同じオブジェクトのセットに対してテーブルビューとリストビューを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="1e853-124">For example, you may want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="1e853-125">選択セットの定義の詳細については、「[選択セットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e853-125">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="1e853-126">カスタムコントロールビューのコンポーネントの詳細については、「[カスタムコントロールの作成](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e853-126">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1e853-127">参照</span><span class="sxs-lookup"><span data-stu-id="1e853-127">See Also</span></span>

[<span data-ttu-id="1e853-128">GroupBy の CustomEntry の EntrySelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="1e853-128">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="1e853-129">カスタム コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="1e853-129">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="1e853-130">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="1e853-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
