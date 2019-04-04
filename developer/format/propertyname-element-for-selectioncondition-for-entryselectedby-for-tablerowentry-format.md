---
title: PropertyName 要素 EntrySelectedBy TableRowEntry (形式) 用の SelectionCondition |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba3b4d9b-2b8c-4a3a-8887-6c606eb9d490
caps.latest.revision: 10
ms.openlocfilehash: 48011950ed64e78a84292762f2c7779003dc59fd
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860988"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format"></a><span data-ttu-id="57631-102">TableRowEntry の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="57631-102">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

<span data-ttu-id="57631-103">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="57631-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="57631-104">このプロパティが存在するかを評価すると`true`条件が満たされると、およびテーブル エントリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="57631-104">When this property is present or when it evaluates to `true`, the condition is met, and the table entry is used.</span></span>

<span data-ttu-id="57631-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableRowEntries 要素 (形式) TableRowEntry 要素 (形式) EntrySelectedBy 要素を TableRowEntry (形式)SelectionCondition EntrySelectedBy TableRowEntry (形式) のための TableRowEntry (形式) PropertyName 要素 EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="57631-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="57631-106">構文</span><span class="sxs-lookup"><span data-stu-id="57631-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="57631-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="57631-107">Attributes and Elements</span></span>

<span data-ttu-id="57631-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`PropertyName`要素。</span><span class="sxs-lookup"><span data-stu-id="57631-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="57631-109">属性</span><span class="sxs-lookup"><span data-stu-id="57631-109">Attributes</span></span>

<span data-ttu-id="57631-110">なし。</span><span class="sxs-lookup"><span data-stu-id="57631-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="57631-111">子要素</span><span class="sxs-lookup"><span data-stu-id="57631-111">Child Elements</span></span>

<span data-ttu-id="57631-112">なし。</span><span class="sxs-lookup"><span data-stu-id="57631-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="57631-113">親要素</span><span class="sxs-lookup"><span data-stu-id="57631-113">Parent Elements</span></span>

|<span data-ttu-id="57631-114">要素</span><span class="sxs-lookup"><span data-stu-id="57631-114">Element</span></span>|<span data-ttu-id="57631-115">説明</span><span class="sxs-lookup"><span data-stu-id="57631-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="57631-116">TableRowEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="57631-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="57631-117">このテーブルのエントリを使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="57631-117">Defines the condition that must exist for this table entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="57631-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="57631-118">Text Value</span></span>

<span data-ttu-id="57631-119">.NET プロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="57631-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="57631-120">コメント</span><span class="sxs-lookup"><span data-stu-id="57631-120">Remarks</span></span>

<span data-ttu-id="57631-121">選択条件では、少なくとも 1 つのプロパティの名前またはスクリプト ブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="57631-121">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="57631-122">選択条件を使用する方法の詳細については、[とビューのエントリの定義の条件またはアイテムが使用されて](./defining-conditions-for-displaying-data.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57631-122">For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="57631-123">テーブル ビューのコンポーネントに関する詳細については、[テーブル ビューを作成する](./creating-a-table-view.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57631-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="57631-124">参照</span><span class="sxs-lookup"><span data-stu-id="57631-124">See Also</span></span>

[<span data-ttu-id="57631-125">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="57631-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="57631-126">データが表示される場合の条件の定義</span><span class="sxs-lookup"><span data-stu-id="57631-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="57631-127">SelectionCondition EntrySelectedBy TableRowEntry (形式) のためのスクリプト ブロックの要素</span><span class="sxs-lookup"><span data-stu-id="57631-127">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="57631-128">TableRowEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="57631-128">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="57631-129">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="57631-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
