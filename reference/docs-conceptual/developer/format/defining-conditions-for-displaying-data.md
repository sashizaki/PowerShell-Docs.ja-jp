---
ms.date: 09/13/2016
ms.topic: reference
title: データの表示条件を定義する
description: データの表示条件を定義する
ms.openlocfilehash: 9a8b7a618da8c64de978c13b527435a2d7793677
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660316"
---
# <a name="defining-conditions-for-displaying-data"></a><span data-ttu-id="71732-103">データの表示条件を定義する</span><span class="sxs-lookup"><span data-stu-id="71732-103">Defining Conditions for Displaying Data</span></span>

<span data-ttu-id="71732-104">ビューまたはコントロールによって表示されるデータを定義するときに、表示されるデータに必要な条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="71732-104">When defining what data is displayed by a view or a control, you can specify a condition that must exist for the data to be displayed.</span></span> <span data-ttu-id="71732-105">条件は、特定のプロパティによって、またはスクリプトまたはプロパティの値がに評価されるときにトリガーされ `true` ます。</span><span class="sxs-lookup"><span data-stu-id="71732-105">The condition can be triggered by a specific property, or when a script or property value evaluates to `true`.</span></span> <span data-ttu-id="71732-106">選択条件が満たされると、ビューまたはコントロールの定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="71732-106">When the selection condition is met, the definition of the view or control is used.</span></span>

## <a name="specifying-a-selection-condition-for-a-definition"></a><span data-ttu-id="71732-107">定義の選択条件の指定</span><span class="sxs-lookup"><span data-stu-id="71732-107">Specifying a Selection Condition for a Definition</span></span>

<span data-ttu-id="71732-108">ビューまたはコントロールの定義を作成するときに、要素を使用して、定義を `EntrySelectedBy` 使用するオブジェクトまたは定義を使用するために必要な条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="71732-108">When creating a definition for a view or control, the `EntrySelectedBy` element is used to specify which objects will use the definition or what condition must exist for the definition to be used.</span></span> <span data-ttu-id="71732-109">条件は、要素によって指定され `SelectionCondition` ます。</span><span class="sxs-lookup"><span data-stu-id="71732-109">The condition is specified by the `SelectionCondition` element.</span></span>

<span data-ttu-id="71732-110">次の例では、テーブルビューの定義に対して選択条件が指定されています。</span><span class="sxs-lookup"><span data-stu-id="71732-110">In the following example, a selection condition is specified for a definition of a table view.</span></span> <span data-ttu-id="71732-111">この例では、指定されたスクリプトがに評価されるときにのみ、定義が使用され `true` ます。</span><span class="sxs-lookup"><span data-stu-id="71732-111">In this example, the definition is used only when the specified script is evaluated to `true`.</span></span>

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

<span data-ttu-id="71732-112">ビューまたはコントロールの定義に指定できる選択条件の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="71732-112">There is no limit to the number of selection conditions that you can specify for a definition of a view or control.</span></span> <span data-ttu-id="71732-113">唯一の要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="71732-113">The only requirements are the following:</span></span>

- <span data-ttu-id="71732-114">選択条件では、条件をトリガーするプロパティ名またはスクリプトを1つ指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="71732-114">The selection condition must specify one property name or script to trigger the condition, but cannot specify both.</span></span>

- <span data-ttu-id="71732-115">選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="71732-115">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

## <a name="specifying-a-selection-condition-for-an-item"></a><span data-ttu-id="71732-116">項目の選択条件の指定</span><span class="sxs-lookup"><span data-stu-id="71732-116">Specifying a Selection Condition for an Item</span></span>

<span data-ttu-id="71732-117">項目定義に要素を含めることによって、リストビューまたはコントロールの項目をいつ使用するかを指定することもでき `ItemSelectionCondition` ます。</span><span class="sxs-lookup"><span data-stu-id="71732-117">You can also specify when an item of a list view or control is used by including the `ItemSelectionCondition` element in the item definition.</span></span> <span data-ttu-id="71732-118">次の例では、リストビューの項目に対して選択条件が指定されています。</span><span class="sxs-lookup"><span data-stu-id="71732-118">In the following example, a selection condition is specified for an item of a list view.</span></span> <span data-ttu-id="71732-119">この例では、項目は、スクリプトがに評価されるときにのみ使用され `true` ます。</span><span class="sxs-lookup"><span data-stu-id="71732-119">In this example, the item is used only when the script is evaluated to `true`.</span></span>

```xml
<ListItem>
  <ItemSelectionCondition>
    <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  </ItemSelectionCondition>
</ListItem>

```

<span data-ttu-id="71732-120">項目の選択条件は1つだけ指定できます。</span><span class="sxs-lookup"><span data-stu-id="71732-120">You can specify only one selection condition for an item.</span></span> <span data-ttu-id="71732-121">条件では、条件をトリガーするプロパティ名またはスクリプトを1つ指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="71732-121">And the condition must specify one property name or script to trigger the condition, but cannot specify both.</span></span>

## <a name="xml-elements"></a><span data-ttu-id="71732-122">XML 要素</span><span class="sxs-lookup"><span data-stu-id="71732-122">XML Elements</span></span>

 <span data-ttu-id="71732-123">次の XML 要素を使用して、選択条件を作成します。</span><span class="sxs-lookup"><span data-stu-id="71732-123">The following XML elements are used to create a selection condition.</span></span>

- <span data-ttu-id="71732-124">次の要素は、ビュー定義の選択条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="71732-124">The following elements specify selection conditions for view definitions:</span></span>

  - [<span data-ttu-id="71732-125">TableControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="71732-125">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

  - [<span data-ttu-id="71732-126">ListControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="71732-126">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

  - [<span data-ttu-id="71732-127">WideControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="71732-127">SelectionCondition Element for EntrySelectedBy for WideControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

  - [<span data-ttu-id="71732-128">CustomControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="71732-128">SelectionCondition Element for EntrySelectedBy for CustomControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

- <span data-ttu-id="71732-129">次の要素は、共通およびビューのコントロール定義の選択条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="71732-129">The following elements specify selection conditions for common and view control definitions:</span></span>

  - [<span data-ttu-id="71732-130">Configuration の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="71732-130">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

  - [<span data-ttu-id="71732-131">View の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="71732-131">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

- <span data-ttu-id="71732-132">次の要素は、コレクションオブジェクトを展開するための選択条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="71732-132">The following element specifies the selection condition for expanding collection objects:</span></span>

  - [<span data-ttu-id="71732-133">EnumerableExpansion の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="71732-133">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

- <span data-ttu-id="71732-134">次の要素は、新しいデータグループを表示するための選択条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="71732-134">The following element specifies the selection condition for displaying a new group of data:</span></span>

  - [<span data-ttu-id="71732-135">GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="71732-135">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

- <span data-ttu-id="71732-136">次の要素は、リストビューの項目選択条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="71732-136">The following element specifies an item selection condition for a list view:</span></span>

  - [<span data-ttu-id="71732-137">ListControl の ListItem の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="71732-137">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

- <span data-ttu-id="71732-138">次の要素は、コントロールの項目選択条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="71732-138">The following elements specify an item selection condition for controls:</span></span>

  - [<span data-ttu-id="71732-139">Configuration の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="71732-139">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

  - [<span data-ttu-id="71732-140">View の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="71732-140">ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

  - [<span data-ttu-id="71732-141">CustomControl の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="71732-141">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

## <a name="see-also"></a><span data-ttu-id="71732-142">参照</span><span class="sxs-lookup"><span data-stu-id="71732-142">See Also</span></span>

[<span data-ttu-id="71732-143">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="71732-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
