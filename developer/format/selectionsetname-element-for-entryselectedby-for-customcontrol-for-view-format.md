---
title: ビュー (形式) のカスタム コントロールの EntrySelectedBy SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 859d2335-7fcd-4efd-b1cc-3d171e334c6b
caps.latest.revision: 7
ms.openlocfilehash: f4bf820be88919af43eeaf043b3ed8b9c06e1bf2
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62063977"
---
# <a name="selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format"></a><span data-ttu-id="8a190-102">View の CustomControl の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="8a190-102">SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)</span></span>

<span data-ttu-id="8a190-103">.NET オブジェクト、リストのエントリのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="8a190-103">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="8a190-104">エントリに指定できる選択セットの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="8a190-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="8a190-105">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) カスタム コントロール要素 (形式) CustomEntries の構成要素のビュー (形式) EntrySelectedBy CustomEntries のビュー (形式) CustomEntry 要素のカスタム コントロールCustomEntry EntrySelectedBy CustomEntry (形式) 用のビュー (形式) SelectionSetName 要素の要素</span><span class="sxs-lookup"><span data-stu-id="8a190-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8a190-106">構文</span><span class="sxs-lookup"><span data-stu-id="8a190-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8a190-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8a190-107">Attributes and Elements</span></span>

<span data-ttu-id="8a190-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionSetName`要素。</span><span class="sxs-lookup"><span data-stu-id="8a190-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8a190-109">属性</span><span class="sxs-lookup"><span data-stu-id="8a190-109">Attributes</span></span>

<span data-ttu-id="8a190-110">なし。</span><span class="sxs-lookup"><span data-stu-id="8a190-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8a190-111">子要素</span><span class="sxs-lookup"><span data-stu-id="8a190-111">Child Elements</span></span>

<span data-ttu-id="8a190-112">なし。</span><span class="sxs-lookup"><span data-stu-id="8a190-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8a190-113">親要素</span><span class="sxs-lookup"><span data-stu-id="8a190-113">Parent Elements</span></span>

|<span data-ttu-id="8a190-114">要素</span><span class="sxs-lookup"><span data-stu-id="8a190-114">Element</span></span>|<span data-ttu-id="8a190-115">説明</span><span class="sxs-lookup"><span data-stu-id="8a190-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8a190-116">表示 (形式) CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="8a190-116">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="8a190-117">このカスタム エントリまたは条件を使用するには、このエントリが存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="8a190-117">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8a190-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="8a190-118">Text Value</span></span>

<span data-ttu-id="8a190-119">選択範囲のセットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="8a190-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="8a190-120">コメント</span><span class="sxs-lookup"><span data-stu-id="8a190-120">Remarks</span></span>

<span data-ttu-id="8a190-121">カスタム コントロールの各エントリに少なくとも 1 つの型名、選択範囲のセット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a190-121">Each custom control entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="8a190-122">複数のビューで使用されるオブジェクトのグループを定義するときに、選択範囲のセットが通常使用されます。</span><span class="sxs-lookup"><span data-stu-id="8a190-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="8a190-123">たとえば、テーブル ビューと同じオブジェクトのセットのリスト ビューを作成する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8a190-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="8a190-124">選択範囲のセットを定義する詳細については、次を参照してください。[選択範囲の設定を定義する](./defining-selection-sets.md)します。</span><span class="sxs-lookup"><span data-stu-id="8a190-124">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="8a190-125">カスタム コントロールのビューのコンポーネントに関する詳細については、次を参照してください。[カスタム コントロールを作成する](./creating-custom-controls.md)します。</span><span class="sxs-lookup"><span data-stu-id="8a190-125">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8a190-126">参照</span><span class="sxs-lookup"><span data-stu-id="8a190-126">See Also</span></span>

[<span data-ttu-id="8a190-127">表示 (形式) CustomEntry EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="8a190-127">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="8a190-128">カスタム コントロールのビュー</span><span class="sxs-lookup"><span data-stu-id="8a190-128">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="8a190-129">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="8a190-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
