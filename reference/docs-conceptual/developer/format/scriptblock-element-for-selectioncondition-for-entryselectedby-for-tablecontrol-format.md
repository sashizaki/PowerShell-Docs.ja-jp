---
title: TableControl による EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b11fbcf-3426-48ae-9319-2c847969f723
caps.latest.revision: 10
ms.openlocfilehash: 7afc834e68ef332bee1e23da782fb5c5527fcf54
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368581"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="e8950-102">TableControl の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e8950-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="e8950-103">条件をトリガーするスクリプトブロックを指定します。</span><span class="sxs-lookup"><span data-stu-id="e8950-103">Specifies the script block that triggers the condition.</span></span> <span data-ttu-id="e8950-104">このスクリプトが `true`に評価されると、条件が満たされ、テーブルエントリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8950-104">When this script is evaluated to `true`, the condition is met, and the table entry is used.</span></span>

<span data-ttu-id="e8950-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries Element (format) TableRowEntry Element (format) TableRowEntry (Format) の要素Entryselectedby for TableRowEntry (Format) の SelectionCondition に対して EntrySelectedBy for TableRowEntry (Format) ScriptBlock 要素の selectioncondition 要素</span><span class="sxs-lookup"><span data-stu-id="e8950-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e8950-106">構文</span><span class="sxs-lookup"><span data-stu-id="e8950-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e8950-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="e8950-107">Attributes and Elements</span></span>

<span data-ttu-id="e8950-108">次のセクションでは、`ScriptBlock` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e8950-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e8950-109">属性</span><span class="sxs-lookup"><span data-stu-id="e8950-109">Attributes</span></span>

<span data-ttu-id="e8950-110">なし。</span><span class="sxs-lookup"><span data-stu-id="e8950-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e8950-111">子要素</span><span class="sxs-lookup"><span data-stu-id="e8950-111">Child Elements</span></span>

<span data-ttu-id="e8950-112">なし。</span><span class="sxs-lookup"><span data-stu-id="e8950-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e8950-113">親要素</span><span class="sxs-lookup"><span data-stu-id="e8950-113">Parent Elements</span></span>

|<span data-ttu-id="e8950-114">要素</span><span class="sxs-lookup"><span data-stu-id="e8950-114">Element</span></span>|<span data-ttu-id="e8950-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="e8950-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e8950-116">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="e8950-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="e8950-117">このテーブルエントリが使用されるために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="e8950-117">Defines the condition that must exist for this table entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e8950-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="e8950-118">Text Value</span></span>

<span data-ttu-id="e8950-119">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e8950-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="e8950-120">コメント</span><span class="sxs-lookup"><span data-stu-id="e8950-120">Remarks</span></span>

<span data-ttu-id="e8950-121">選択条件では、少なくとも1つのスクリプトブロックまたはプロパティ名を指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e8950-121">The selection condition must specify at least one script block or property name, but cannot specify both.</span></span> <span data-ttu-id="e8950-122">選択条件の使用方法の詳細については、「[ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8950-122">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="e8950-123">テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8950-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e8950-124">参照</span><span class="sxs-lookup"><span data-stu-id="e8950-124">See Also</span></span>

[<span data-ttu-id="e8950-125">テーブルビューの作成</span><span class="sxs-lookup"><span data-stu-id="e8950-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="e8950-126">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="e8950-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="e8950-127">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="e8950-127">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[<span data-ttu-id="e8950-128">TableRowEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="e8950-128">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="e8950-129">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="e8950-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
