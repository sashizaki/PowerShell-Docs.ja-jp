---
title: データを表示するための条件を定義する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1e05821-6aec-437b-84a5-218a5727f88b
caps.latest.revision: 10
ms.openlocfilehash: 8a5b84b6a461e9fc340a5981578d95ca2ac6b9f7
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363901"
---
# <a name="defining-conditions-for-displaying-data"></a><span data-ttu-id="cfcf2-102">データの表示条件を定義する</span><span class="sxs-lookup"><span data-stu-id="cfcf2-102">Defining Conditions for Displaying Data</span></span>

<span data-ttu-id="cfcf2-103">ビューまたはコントロールによって表示されるデータを定義するときに、表示されるデータに必要な条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="cfcf2-103">When defining what data is displayed by a view or a control, you can specify a condition that must exist for the data to be displayed.</span></span> <span data-ttu-id="cfcf2-104">条件は、特定のプロパティによって、またはスクリプトまたはプロパティの値が `true`に評価されるときにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="cfcf2-104">The condition can be triggered by a specific property, or when a script or property value evaluates to `true`.</span></span> <span data-ttu-id="cfcf2-105">選択条件が満たされると、ビューまたはコントロールの定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="cfcf2-105">When the selection condition is met, the definition of the view or control is used.</span></span>

## <a name="specifying-a-selection-condition-for-a-definition"></a><span data-ttu-id="cfcf2-106">定義の選択条件の指定</span><span class="sxs-lookup"><span data-stu-id="cfcf2-106">Specifying a Selection Condition for a Definition</span></span>

<span data-ttu-id="cfcf2-107">ビューまたはコントロールの定義を作成するときに、`EntrySelectedBy` 要素を使用して、定義を使用するオブジェクトまたは定義を使用するために必要な条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="cfcf2-107">When creating a definition for a view or control, the `EntrySelectedBy` element is used to specify which objects will use the definition or what condition must exist for the definition to be used.</span></span> <span data-ttu-id="cfcf2-108">条件は `SelectionCondition` 要素によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="cfcf2-108">The condition is specified by the `SelectionCondition` element.</span></span>

<span data-ttu-id="cfcf2-109">次の例では、テーブルビューの定義に対して選択条件が指定されています。</span><span class="sxs-lookup"><span data-stu-id="cfcf2-109">In the following example, a selection condition is specified for a definition of a table view.</span></span> <span data-ttu-id="cfcf2-110">この例では、指定されたスクリプトが `true`に評価される場合にのみ、定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="cfcf2-110">In this example, the definition is used only when the specified script is evaluated to `true`.</span></span>

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <SelectionCondition>
      <ScriptBlock>ScriptToEvaluate</ScriptBlock>
    </SelectionCondition>
  </EntrySelectedBy>
  <TableColumnItems>
  </TableColumnItems>
</TableRowEntry>

```

<span data-ttu-id="cfcf2-111">ビューまたはコントロールの定義に指定できる選択条件の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="cfcf2-111">There is no limit to the number of selection conditions that you can specify for a definition of a view or control.</span></span> <span data-ttu-id="cfcf2-112">唯一の要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cfcf2-112">The only requirements are the following:</span></span>

- <span data-ttu-id="cfcf2-113">選択条件では、条件をトリガーするプロパティ名またはスクリプトを1つ指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="cfcf2-113">The selection condition must specify one property name or script to trigger the condition, but cannot specify both.</span></span>

- <span data-ttu-id="cfcf2-114">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="cfcf2-114">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

## <a name="specifying-a-selection-condition-for-an-item"></a><span data-ttu-id="cfcf2-115">項目の選択条件の指定</span><span class="sxs-lookup"><span data-stu-id="cfcf2-115">Specifying a Selection Condition for an Item</span></span>

<span data-ttu-id="cfcf2-116">項目定義に `ItemSelectionCondition` 要素を含めることによって、リストビューまたはコントロールの項目をいつ使用するかを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="cfcf2-116">You can also specify when an item of a list view or control is used by including the `ItemSelectionCondition` element in the item definition.</span></span> <span data-ttu-id="cfcf2-117">次の例では、リストビューの項目に対して選択条件が指定されています。</span><span class="sxs-lookup"><span data-stu-id="cfcf2-117">In the following example, a selection condition is specified for an item of a list view.</span></span> <span data-ttu-id="cfcf2-118">この例では、この項目は、スクリプトが `true`に評価されるときにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="cfcf2-118">In this example, the item is used only when the script is evaluated to `true`.</span></span>

```xml
<ListItem>
  <ItemSelectionCondition>
    <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  </ItemSelectionCondition>
</ListItem>

```

<span data-ttu-id="cfcf2-119">項目の選択条件は1つだけ指定できます。</span><span class="sxs-lookup"><span data-stu-id="cfcf2-119">You can specify only one selection condition for an item.</span></span> <span data-ttu-id="cfcf2-120">条件では、条件をトリガーするプロパティ名またはスクリプトを1つ指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="cfcf2-120">And the condition must specify one property name or script to trigger the condition, but cannot specify both.</span></span>

## <a name="xml-elements"></a><span data-ttu-id="cfcf2-121">XML 要素</span><span class="sxs-lookup"><span data-stu-id="cfcf2-121">XML Elements</span></span>

 <span data-ttu-id="cfcf2-122">次の XML 要素を使用して、選択条件を作成します。</span><span class="sxs-lookup"><span data-stu-id="cfcf2-122">The following XML elements are used to create a selection condition.</span></span>

- <span data-ttu-id="cfcf2-123">次の要素は、ビュー定義の選択条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="cfcf2-123">The following elements specify selection conditions for view definitions:</span></span>

    - [<span data-ttu-id="cfcf2-124">TableControl の EntrySelectedBy の SelectionCondition 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="cfcf2-124">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

    - [<span data-ttu-id="cfcf2-125">ListControl (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="cfcf2-125">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

    - [<span data-ttu-id="cfcf2-126">WideControl (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="cfcf2-126">SelectionCondition Element for EntrySelectedBy for WideControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

    - [<span data-ttu-id="cfcf2-127">CustomControl (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="cfcf2-127">SelectionCondition Element for EntrySelectedBy for CustomControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

- <span data-ttu-id="cfcf2-128">次の要素は、共通およびビューのコントロール定義の選択条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="cfcf2-128">The following elements specify selection conditions for common and view control definitions:</span></span>

    - [<span data-ttu-id="cfcf2-129">構成用のコントロール (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="cfcf2-129">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

    - [<span data-ttu-id="cfcf2-130">ビューのコントロール (Format) に対する EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="cfcf2-130">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

- <span data-ttu-id="cfcf2-131">次の要素は、コレクションオブジェクトを展開するための選択条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="cfcf2-131">The following element specifies the selection condition for expanding collection objects:</span></span>

    - [<span data-ttu-id="cfcf2-132">列挙 Able膨張 (形式) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="cfcf2-132">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

- <span data-ttu-id="cfcf2-133">次の要素は、新しいデータグループを表示するための選択条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="cfcf2-133">The following element specifies the selection condition for displaying a new group of data:</span></span>

    - [<span data-ttu-id="cfcf2-134">GroupBy (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="cfcf2-134">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

- <span data-ttu-id="cfcf2-135">次の要素は、リストビューの項目選択条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="cfcf2-135">The following element specifies an item selection condition for a list view:</span></span>

    - [<span data-ttu-id="cfcf2-136">ListControl の ListItem の ItemSelectionCondition 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="cfcf2-136">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

- <span data-ttu-id="cfcf2-137">次の要素は、コントロールの項目選択条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="cfcf2-137">The following elements specify an item selection condition for controls:</span></span>

    - [<span data-ttu-id="cfcf2-138">構成用のコントロールの式のバインドの ItemSelectionCondition 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="cfcf2-138">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

    - [<span data-ttu-id="cfcf2-139">ビューのコントロール (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="cfcf2-139">ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

    - [<span data-ttu-id="cfcf2-140">CustomControl (Format) の式のバインドの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="cfcf2-140">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

## <a name="see-also"></a><span data-ttu-id="cfcf2-141">参照</span><span class="sxs-lookup"><span data-stu-id="cfcf2-141">See Also</span></span>

[<span data-ttu-id="cfcf2-142">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="cfcf2-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
