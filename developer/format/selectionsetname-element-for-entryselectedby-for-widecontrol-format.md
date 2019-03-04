---
title: WideControl (形式) の EntrySelectedBy SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c9c6e18f-6cca-465c-bd20-3969e7897a96
caps.latest.revision: 10
ms.openlocfilehash: 6b6a4a4647412d11d947f1dc4ea12d1e05ff536e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856798"
---
# <a name="selectionsetname-element-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="e9ae2-102">WideControl の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e9ae2-102">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="e9ae2-103">一連の定義については、.NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-103">Specifies a set of .NET objects for the definition.</span></span> <span data-ttu-id="e9ae2-104">これらのオブジェクトのいずれかが表示されるたびに、定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-104">The definition is used whenever one of these objects is displayed.</span></span>

<span data-ttu-id="e9ae2-105">構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式) WideEntry 要素 (形式) EntrySelectedBy 要素の WideEntry (形式) SelectionSetName 要素EntrySelectedBy WideEntry (形式) の</span><span class="sxs-lookup"><span data-stu-id="e9ae2-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e9ae2-106">構文</span><span class="sxs-lookup"><span data-stu-id="e9ae2-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="e9ae2-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="e9ae2-107">Attributes and Elements</span></span>

<span data-ttu-id="e9ae2-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionSetName`要素。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-108">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e9ae2-109">属性</span><span class="sxs-lookup"><span data-stu-id="e9ae2-109">Attributes</span></span>

<span data-ttu-id="e9ae2-110">なし。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e9ae2-111">子要素</span><span class="sxs-lookup"><span data-stu-id="e9ae2-111">Child Elements</span></span>

<span data-ttu-id="e9ae2-112">なし。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e9ae2-113">親要素</span><span class="sxs-lookup"><span data-stu-id="e9ae2-113">Parent Elements</span></span>

|<span data-ttu-id="e9ae2-114">要素</span><span class="sxs-lookup"><span data-stu-id="e9ae2-114">Element</span></span>|<span data-ttu-id="e9ae2-115">説明</span><span class="sxs-lookup"><span data-stu-id="e9ae2-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e9ae2-116">WideEntry (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="e9ae2-116">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="e9ae2-117">このワイド エントリまたは条件を使用するには、このエントリが存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-117">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e9ae2-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="e9ae2-118">Text Value</span></span>

<span data-ttu-id="e9ae2-119">選択範囲のセットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="e9ae2-120">コメント</span><span class="sxs-lookup"><span data-stu-id="e9ae2-120">Remarks</span></span>

<span data-ttu-id="e9ae2-121">各定義には、1 つの型名、選択範囲のセット、または選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-121">Each definition must specify one type name, selection set, or selection condition.</span></span>

<span data-ttu-id="e9ae2-122">複数のビューで使用されるオブジェクトのグループを定義するときに、選択範囲のセットが通常使用されます。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="e9ae2-123">たとえば、テーブル ビューと同じオブジェクトのセットのリスト ビューを作成する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="e9ae2-124">選択範囲のセットを定義する詳細については、次を参照してください。[を定義する設定のビューのオブジェクトを](./defining-selection-sets.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-124">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="e9ae2-125">ワイド ビューの他のコンポーネントに関する詳細については、次を参照してください。[ワイド ビューを作成する](./creating-a-wide-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-125">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e9ae2-126">参照</span><span class="sxs-lookup"><span data-stu-id="e9ae2-126">See Also</span></span>

[<span data-ttu-id="e9ae2-127">ワイド ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="e9ae2-128">選択範囲のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-128">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="e9ae2-129">WideEntry (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="e9ae2-129">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="e9ae2-130">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="e9ae2-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
