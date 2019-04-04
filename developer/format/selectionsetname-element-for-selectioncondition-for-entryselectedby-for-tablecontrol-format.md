---
title: TableControl (形式) の EntrySelectedBy の SelectionCondition SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17ae4d6b-dc95-4a1d-8e32-31ff084a951f
caps.latest.revision: 10
ms.openlocfilehash: edb163f2b0b5129bd741677dce882888d9bbfd89
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56863278"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="133ce-102">TableControl の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="133ce-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="133ce-103">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="133ce-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="133ce-104">このセット内の型のいずれかが存在して、条件が満たされると、テーブル ビューのこの定義を使用して、オブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="133ce-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the table view.</span></span>

<span data-ttu-id="133ce-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableRowEntries 要素 (形式) TableRowEntry 要素 (形式) EntrySelectedBy 要素を TableRowEntry (形式)SelectionCondition EntrySelectedBy TableRowEntry (形式) のための TableRowEntry (形式) SelectionSetName 要素 EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="133ce-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="133ce-106">構文</span><span class="sxs-lookup"><span data-stu-id="133ce-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="133ce-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="133ce-107">Attributes and Elements</span></span>

<span data-ttu-id="133ce-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionSetName`要素。</span><span class="sxs-lookup"><span data-stu-id="133ce-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="133ce-109">属性</span><span class="sxs-lookup"><span data-stu-id="133ce-109">Attributes</span></span>

<span data-ttu-id="133ce-110">なし。</span><span class="sxs-lookup"><span data-stu-id="133ce-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="133ce-111">子要素</span><span class="sxs-lookup"><span data-stu-id="133ce-111">Child Elements</span></span>

<span data-ttu-id="133ce-112">なし。</span><span class="sxs-lookup"><span data-stu-id="133ce-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="133ce-113">親要素</span><span class="sxs-lookup"><span data-stu-id="133ce-113">Parent Elements</span></span>

|<span data-ttu-id="133ce-114">要素</span><span class="sxs-lookup"><span data-stu-id="133ce-114">Element</span></span>|<span data-ttu-id="133ce-115">説明</span><span class="sxs-lookup"><span data-stu-id="133ce-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="133ce-116">TableRowEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="133ce-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="133ce-117">テーブル ビューのこの定義に使用する必要があります条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="133ce-117">Defines the condition that must exist to use for this definition of the table view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="133ce-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="133ce-118">Text Value</span></span>

<span data-ttu-id="133ce-119">選択範囲のセットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="133ce-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="133ce-120">コメント</span><span class="sxs-lookup"><span data-stu-id="133ce-120">Remarks</span></span>

<span data-ttu-id="133ce-121">選択条件では、選択範囲のセットまたは .NET の型を指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="133ce-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="133ce-122">選択条件を使用する方法の詳細については、[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="133ce-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="133ce-123">選択範囲のセットは、書式設定ファイルを定義する任意のビューで使用できる .NET オブジェクトの一般的なグループです。</span><span class="sxs-lookup"><span data-stu-id="133ce-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="133ce-124">作成と選択範囲のセットの参照の詳細については、[オブジェクト設定を定義する](./defining-selection-sets.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="133ce-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="133ce-125">ワイド ビューの他のコンポーネントに関する詳細については、[テーブル ビューを作成する](./creating-a-table-view.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="133ce-125">For more information about other components of a wide view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="133ce-126">参照</span><span class="sxs-lookup"><span data-stu-id="133ce-126">See Also</span></span>

[<span data-ttu-id="133ce-127">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="133ce-127">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="133ce-128">データが表示される場合の条件の定義</span><span class="sxs-lookup"><span data-stu-id="133ce-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="133ce-129">SelectionCondition EntrySelectedBy TableRowEntry (形式) のための TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="133ce-129">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="133ce-130">TableRowEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="133ce-130">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="133ce-131">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="133ce-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
