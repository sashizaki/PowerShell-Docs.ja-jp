---
title: TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の PropertyName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba3b4d9b-2b8c-4a3a-8887-6c606eb9d490
caps.latest.revision: 10
ms.openlocfilehash: 48011950ed64e78a84292762f2c7779003dc59fd
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365001"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format"></a><span data-ttu-id="21dbd-102">TableRowEntry の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="21dbd-102">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

<span data-ttu-id="21dbd-103">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="21dbd-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="21dbd-104">このプロパティが存在する場合、または `true`に評価された場合、条件が満たされ、テーブルエントリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="21dbd-104">When this property is present or when it evaluates to `true`, the condition is met, and the table entry is used.</span></span>

<span data-ttu-id="21dbd-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries Element (format) TableRowEntry Element (format) TableRowEntry (Format) の要素Entryselectedby for TableRowEntry (Format) の SelectionCondition に対して EntrySelectedBy の TableRowEntry (Format) PropertyName 要素の selectioncondition 要素</span><span class="sxs-lookup"><span data-stu-id="21dbd-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="21dbd-106">構文</span><span class="sxs-lookup"><span data-stu-id="21dbd-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="21dbd-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="21dbd-107">Attributes and Elements</span></span>

<span data-ttu-id="21dbd-108">次のセクションでは、`PropertyName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="21dbd-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="21dbd-109">属性</span><span class="sxs-lookup"><span data-stu-id="21dbd-109">Attributes</span></span>

<span data-ttu-id="21dbd-110">なし。</span><span class="sxs-lookup"><span data-stu-id="21dbd-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="21dbd-111">子要素</span><span class="sxs-lookup"><span data-stu-id="21dbd-111">Child Elements</span></span>

<span data-ttu-id="21dbd-112">なし。</span><span class="sxs-lookup"><span data-stu-id="21dbd-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="21dbd-113">親要素</span><span class="sxs-lookup"><span data-stu-id="21dbd-113">Parent Elements</span></span>

|<span data-ttu-id="21dbd-114">要素</span><span class="sxs-lookup"><span data-stu-id="21dbd-114">Element</span></span>|<span data-ttu-id="21dbd-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="21dbd-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="21dbd-116">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="21dbd-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="21dbd-117">このテーブルエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="21dbd-117">Defines the condition that must exist for this table entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="21dbd-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="21dbd-118">Text Value</span></span>

<span data-ttu-id="21dbd-119">.NET プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="21dbd-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="21dbd-120">コメント</span><span class="sxs-lookup"><span data-stu-id="21dbd-120">Remarks</span></span>

<span data-ttu-id="21dbd-121">選択条件では、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="21dbd-121">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="21dbd-122">選択条件を使用する方法の詳細については、「[ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21dbd-122">For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="21dbd-123">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21dbd-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="21dbd-124">参照</span><span class="sxs-lookup"><span data-stu-id="21dbd-124">See Also</span></span>

[<span data-ttu-id="21dbd-125">テーブルビューの作成</span><span class="sxs-lookup"><span data-stu-id="21dbd-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="21dbd-126">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="21dbd-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="21dbd-127">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素</span><span class="sxs-lookup"><span data-stu-id="21dbd-127">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="21dbd-128">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="21dbd-128">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="21dbd-129">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="21dbd-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
