---
title: CustomControl for View (Format) の EntrySelectedBy の SelectionSetName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 859d2335-7fcd-4efd-b1cc-3d171e334c6b
caps.latest.revision: 7
ms.openlocfilehash: f4bf820be88919af43eeaf043b3ed8b9c06e1bf2
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364751"
---
# <a name="selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format"></a><span data-ttu-id="92821-102">View の CustomControl の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="92821-102">SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)</span></span>

<span data-ttu-id="92821-103">リストエントリの一連の .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="92821-103">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="92821-104">エントリに指定できる選択セットの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="92821-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="92821-105">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (Format) CustomControl 要素 (形式) の CustomEntries 要素の CustomControl for view (format) EntrySelectedBy 要素 for view (Format) EntrySelectedByCustomEntry (形式) の EntrySelectedBy for View (Format) SelectionSetName 要素の要素</span><span class="sxs-lookup"><span data-stu-id="92821-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="92821-106">構文</span><span class="sxs-lookup"><span data-stu-id="92821-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="92821-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="92821-107">Attributes and Elements</span></span>

<span data-ttu-id="92821-108">次のセクションでは、属性、子要素、`SelectionSetName` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="92821-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="92821-109">属性</span><span class="sxs-lookup"><span data-stu-id="92821-109">Attributes</span></span>

<span data-ttu-id="92821-110">なし。</span><span class="sxs-lookup"><span data-stu-id="92821-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="92821-111">子要素</span><span class="sxs-lookup"><span data-stu-id="92821-111">Child Elements</span></span>

<span data-ttu-id="92821-112">なし。</span><span class="sxs-lookup"><span data-stu-id="92821-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="92821-113">親要素</span><span class="sxs-lookup"><span data-stu-id="92821-113">Parent Elements</span></span>

|<span data-ttu-id="92821-114">要素</span><span class="sxs-lookup"><span data-stu-id="92821-114">Element</span></span>|<span data-ttu-id="92821-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="92821-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="92821-116">CustomEntry for ビューの EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="92821-116">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="92821-117">このカスタムエントリを使用する .NET 型、またはこのエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="92821-117">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="92821-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="92821-118">Text Value</span></span>

<span data-ttu-id="92821-119">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="92821-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="92821-120">コメント</span><span class="sxs-lookup"><span data-stu-id="92821-120">Remarks</span></span>

<span data-ttu-id="92821-121">各カスタムコントロールエントリには、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="92821-121">Each custom control entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="92821-122">選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="92821-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="92821-123">たとえば、同じオブジェクトのセットに対してテーブルビューとリストビューを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="92821-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="92821-124">選択セットの定義の詳細については、「[選択セットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92821-124">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="92821-125">カスタムコントロールビューのコンポーネントの詳細については、「[カスタムコントロールの作成](./creating-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92821-125">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="92821-126">参照</span><span class="sxs-lookup"><span data-stu-id="92821-126">See Also</span></span>

[<span data-ttu-id="92821-127">CustomEntry for ビューの EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="92821-127">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="92821-128">カスタムコントロールビュー</span><span class="sxs-lookup"><span data-stu-id="92821-128">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="92821-129">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="92821-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
