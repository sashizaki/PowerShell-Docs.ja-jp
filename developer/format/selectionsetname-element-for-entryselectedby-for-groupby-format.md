---
title: GroupBy (形式) の EntrySelectedBy SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d569c623-2277-49e3-933e-c26262b91cd5
caps.latest.revision: 6
ms.openlocfilehash: 69cd113c444b4e3c5dceabcdfddb439cd1376f6b
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858858"
---
# <a name="selectionsetname-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="a900b-102">GroupBy の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a900b-102">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="a900b-103">.NET オブジェクト、リストのエントリのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="a900b-103">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="a900b-104">エントリに指定できる選択セットの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="a900b-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span> <span data-ttu-id="a900b-105">この要素は、オブジェクトの新しいグループを表示する方法を定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a900b-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="a900b-106">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) GroupBy 要素の GroupBy (形式) CustomEntry 要素にカスタム コントロールの GroupBy (形式) CustomEntries 要素のカスタム コントロール要素をビュー (形式)GroupBy (形式) の EntrySelectedBy の GroupBy (形式) SelectionSetName 要素 CustomEntry の GroupBy (形式) EntrySelectedBy 要素にカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="a900b-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a900b-107">構文</span><span class="sxs-lookup"><span data-stu-id="a900b-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a900b-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="a900b-108">Attributes and Elements</span></span>

<span data-ttu-id="a900b-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionSetName`要素。</span><span class="sxs-lookup"><span data-stu-id="a900b-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a900b-110">属性</span><span class="sxs-lookup"><span data-stu-id="a900b-110">Attributes</span></span>

<span data-ttu-id="a900b-111">なし。</span><span class="sxs-lookup"><span data-stu-id="a900b-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a900b-112">子要素</span><span class="sxs-lookup"><span data-stu-id="a900b-112">Child Elements</span></span>

<span data-ttu-id="a900b-113">なし。</span><span class="sxs-lookup"><span data-stu-id="a900b-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a900b-114">親要素</span><span class="sxs-lookup"><span data-stu-id="a900b-114">Parent Elements</span></span>

|<span data-ttu-id="a900b-115">要素</span><span class="sxs-lookup"><span data-stu-id="a900b-115">Element</span></span>|<span data-ttu-id="a900b-116">説明</span><span class="sxs-lookup"><span data-stu-id="a900b-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a900b-117">GroupBy (形式) の CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="a900b-117">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="a900b-118">このカスタム エントリまたは条件を使用するには、このエントリが存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="a900b-118">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a900b-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="a900b-119">Text Value</span></span>

<span data-ttu-id="a900b-120">選択範囲のセットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a900b-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="a900b-121">コメント</span><span class="sxs-lookup"><span data-stu-id="a900b-121">Remarks</span></span>

<span data-ttu-id="a900b-122">各カスタム コントロールの定義に少なくとも 1 つの型名、選択範囲のセット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a900b-122">Each custom control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="a900b-123">複数のビューで使用されるオブジェクトのグループを定義するときに、選択範囲のセットが通常使用されます。</span><span class="sxs-lookup"><span data-stu-id="a900b-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="a900b-124">たとえば、テーブル ビューと同じオブジェクトのセットのリスト ビューを作成する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a900b-124">For example, you may want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="a900b-125">選択範囲のセットを定義する詳細については、[選択範囲の設定を定義する](./defining-selection-sets.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a900b-125">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="a900b-126">カスタム コントロールのビューのコンポーネントに関する詳細については、[カスタム コントロールを作成する](./creating-custom-controls.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a900b-126">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a900b-127">参照</span><span class="sxs-lookup"><span data-stu-id="a900b-127">See Also</span></span>

[<span data-ttu-id="a900b-128">GroupBy (形式) の CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="a900b-128">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="a900b-129">カスタム コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="a900b-129">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="a900b-130">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="a900b-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
