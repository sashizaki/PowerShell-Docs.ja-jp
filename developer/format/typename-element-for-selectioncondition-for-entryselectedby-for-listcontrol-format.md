---
title: SelectionCondition EntrySelectedBy ListControl (形式) のための TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd025a3a-3780-40db-a068-873e7df38015
caps.latest.revision: 9
ms.openlocfilehash: 2b76b040b39088cc9c3b9d6890c38df3c533b39f
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862778"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="47323-102">ListControl の EntrySelectedBy の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="47323-102">TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="47323-103">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="47323-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="47323-104">この型が存在するときに、一覧のエントリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="47323-104">When this type is present, the list entry is used.</span></span>

<span data-ttu-id="47323-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) ListControl 要素 (形式) ListEntries 要素の要素に ListControl (形式) ListEntry ListEntries の ListControl (形式) EntrySelectedBy 要素のListEntry SelectionCondition EntrySelectedBy ListControl (形式) のための ListControl (形式) の TypeName 要素 EntrySelectedBy の ListControl (形式) SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="47323-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format) SelectionCondition Element for EntrySelectedBy for ListControl (Format) TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="47323-106">構文</span><span class="sxs-lookup"><span data-stu-id="47323-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="47323-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="47323-107">Attributes and Elements</span></span>

<span data-ttu-id="47323-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`TypeName`要素。</span><span class="sxs-lookup"><span data-stu-id="47323-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="47323-109">属性</span><span class="sxs-lookup"><span data-stu-id="47323-109">Attributes</span></span>

<span data-ttu-id="47323-110">なし。</span><span class="sxs-lookup"><span data-stu-id="47323-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="47323-111">子要素</span><span class="sxs-lookup"><span data-stu-id="47323-111">Child Elements</span></span>

<span data-ttu-id="47323-112">なし。</span><span class="sxs-lookup"><span data-stu-id="47323-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="47323-113">親要素</span><span class="sxs-lookup"><span data-stu-id="47323-113">Parent Elements</span></span>

|<span data-ttu-id="47323-114">要素</span><span class="sxs-lookup"><span data-stu-id="47323-114">Element</span></span>|<span data-ttu-id="47323-115">説明</span><span class="sxs-lookup"><span data-stu-id="47323-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="47323-116">ListControl (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="47323-116">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="47323-117">このリストのエントリを使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="47323-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="47323-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="47323-118">Text Value</span></span>

<span data-ttu-id="47323-119">.NET 型の完全修飾名を指定します。`System.IO.DirectoryInfo`します。</span><span class="sxs-lookup"><span data-stu-id="47323-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="47323-120">コメント</span><span class="sxs-lookup"><span data-stu-id="47323-120">Remarks</span></span>

<span data-ttu-id="47323-121">選択条件が .NET 型の任意の数を指定するか、選択範囲を設定するが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="47323-121">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="47323-122">選択条件を使用する方法の詳細については、次を参照してください。[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="47323-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="47323-123">その他の詳細については、リスト ビューのコンポーネントを参照してください[リスト ビューを作成する](./creating-a-list-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="47323-123">For more information about other the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="47323-124">参照</span><span class="sxs-lookup"><span data-stu-id="47323-124">See Also</span></span>

[<span data-ttu-id="47323-125">リスト ビューの作成</span><span class="sxs-lookup"><span data-stu-id="47323-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="47323-126">データが表示される場合の条件の定義</span><span class="sxs-lookup"><span data-stu-id="47323-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="47323-127">ListControl (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="47323-127">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="47323-128">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="47323-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
