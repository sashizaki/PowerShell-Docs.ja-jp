---
title: TableControl の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17ae4d6b-dc95-4a1d-8e32-31ff084a951f
caps.latest.revision: 10
ms.openlocfilehash: edb163f2b0b5129bd741677dce882888d9bbfd89
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361921"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="38b6d-102">TableControl の EntrySelectedBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="38b6d-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="38b6d-103">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="38b6d-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="38b6d-104">このセット内のいずれかの型が存在する場合、条件が満たされ、テーブルビューのこの定義を使用してオブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38b6d-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the table view.</span></span>

<span data-ttu-id="38b6d-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries Element (format) TableRowEntry Element (format) TableRowEntry (Format) の要素TableRowEntry (format) 用の EntrySelectedBy for TableRowEntry (Format) の SelectionSetName 要素の selectioncondition 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="38b6d-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="38b6d-106">構文</span><span class="sxs-lookup"><span data-stu-id="38b6d-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="38b6d-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="38b6d-107">Attributes and Elements</span></span>

<span data-ttu-id="38b6d-108">次のセクションでは、`SelectionSetName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="38b6d-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="38b6d-109">属性</span><span class="sxs-lookup"><span data-stu-id="38b6d-109">Attributes</span></span>

<span data-ttu-id="38b6d-110">なし。</span><span class="sxs-lookup"><span data-stu-id="38b6d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="38b6d-111">子要素</span><span class="sxs-lookup"><span data-stu-id="38b6d-111">Child Elements</span></span>

<span data-ttu-id="38b6d-112">なし。</span><span class="sxs-lookup"><span data-stu-id="38b6d-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="38b6d-113">親要素</span><span class="sxs-lookup"><span data-stu-id="38b6d-113">Parent Elements</span></span>

|<span data-ttu-id="38b6d-114">要素</span><span class="sxs-lookup"><span data-stu-id="38b6d-114">Element</span></span>|<span data-ttu-id="38b6d-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="38b6d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="38b6d-116">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="38b6d-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="38b6d-117">テーブルビューのこの定義に使用する必要がある条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="38b6d-117">Defines the condition that must exist to use for this definition of the table view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="38b6d-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="38b6d-118">Text Value</span></span>

<span data-ttu-id="38b6d-119">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="38b6d-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="38b6d-120">コメント</span><span class="sxs-lookup"><span data-stu-id="38b6d-120">Remarks</span></span>

<span data-ttu-id="38b6d-121">選択条件では、選択セットまたは .NET 型を指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="38b6d-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="38b6d-122">選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38b6d-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="38b6d-123">選択セットは、書式設定ファイルによって定義される任意のビューで使用できる .NET オブジェクトの一般的なグループです。</span><span class="sxs-lookup"><span data-stu-id="38b6d-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="38b6d-124">選択セットの作成と参照の詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38b6d-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="38b6d-125">ワイドビューのその他のコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38b6d-125">For more information about other components of a wide view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="38b6d-126">参照</span><span class="sxs-lookup"><span data-stu-id="38b6d-126">See Also</span></span>

[<span data-ttu-id="38b6d-127">テーブルビューの作成</span><span class="sxs-lookup"><span data-stu-id="38b6d-127">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="38b6d-128">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="38b6d-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="38b6d-129">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="38b6d-129">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="38b6d-130">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="38b6d-130">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="38b6d-131">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="38b6d-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
