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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855648"
---
# <a name="defining-conditions-for-displaying-data"></a><span data-ttu-id="5955f-102">データの表示条件を定義する</span><span class="sxs-lookup"><span data-stu-id="5955f-102">Defining Conditions for Displaying Data</span></span>

<span data-ttu-id="5955f-103">ビューまたはコントロールを表示するデータを定義するときは、データを表示するのに必要な条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5955f-103">When defining what data is displayed by a view or a control, you can specify a condition that must exist for the data to be displayed.</span></span> <span data-ttu-id="5955f-104">ときに、スクリプトまたは特定のプロパティによって、条件がトリガーされることができます、プロパティの値として評価または`true`します。</span><span class="sxs-lookup"><span data-stu-id="5955f-104">The condition can be triggered by a specific property, or when a script or property value evaluates to `true`.</span></span> <span data-ttu-id="5955f-105">選択条件が満たされたときに、ビューまたはコントロールの定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5955f-105">When the selection condition is met, the definition of the view or control is used.</span></span>

## <a name="specifying-a-selection-condition-for-a-definition"></a><span data-ttu-id="5955f-106">定義の選択条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="5955f-106">Specifying a Selection Condition for a Definition</span></span>

<span data-ttu-id="5955f-107">ビューまたはコントロールの定義を作成するときに、`EntrySelectedBy`要素を使用して、オブジェクトの定義が使用または使用する定義の条件が存在する必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="5955f-107">When creating a definition for a view or control, the `EntrySelectedBy` element is used to specify which objects will use the definition or what condition must exist for the definition to be used.</span></span> <span data-ttu-id="5955f-108">条件が指定された、`SelectionCondition`要素。</span><span class="sxs-lookup"><span data-stu-id="5955f-108">The condition is specified by the `SelectionCondition` element.</span></span>

<span data-ttu-id="5955f-109">次の例では、選択条件を指定して、テーブル ビューの定義についてはします。</span><span class="sxs-lookup"><span data-stu-id="5955f-109">In the following example, a selection condition is specified for a definition of a table view.</span></span> <span data-ttu-id="5955f-110">この例で定義を使用する、指定したスクリプトが評価されるときにのみ`true`します。</span><span class="sxs-lookup"><span data-stu-id="5955f-110">In this example, the definition is used only when the specified script is evaluated to `true`.</span></span>

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

<span data-ttu-id="5955f-111">ビューまたはコントロールの定義に指定できる選択条件の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="5955f-111">There is no limit to the number of selection conditions that you can specify for a definition of a view or control.</span></span> <span data-ttu-id="5955f-112">唯一の要件は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5955f-112">The only requirements are the following:</span></span>

- <span data-ttu-id="5955f-113">選択条件では、1 つのプロパティ名またはスクリプトを起動するトリガーの条件を指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="5955f-113">The selection condition must specify one property name or script to trigger the condition, but cannot specify both.</span></span>

- <span data-ttu-id="5955f-114">選択条件が .NET 型の任意の数を指定するか、選択範囲を設定するが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="5955f-114">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

## <a name="specifying-a-selection-condition-for-an-item"></a><span data-ttu-id="5955f-115">項目の選択条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="5955f-115">Specifying a Selection Condition for an Item</span></span>

<span data-ttu-id="5955f-116">含めることによってリスト ビューまたはコントロールの項目を使用する場合を指定することも、`ItemSelectionCondition`アイテム定義内の要素。</span><span class="sxs-lookup"><span data-stu-id="5955f-116">You can also specify when an item of a list view or control is used by including the `ItemSelectionCondition` element in the item definition.</span></span> <span data-ttu-id="5955f-117">次の例では、選択条件を指定して、リスト ビューの項目の。</span><span class="sxs-lookup"><span data-stu-id="5955f-117">In the following example, a selection condition is specified for an item of a list view.</span></span> <span data-ttu-id="5955f-118">この例で、項目を使用するスクリプトが評価される場合にのみ`true`します。</span><span class="sxs-lookup"><span data-stu-id="5955f-118">In this example, the item is used only when the script is evaluated to `true`.</span></span>

```xml
<ListItem>
  <ItemSelectionCondition>
    <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  </ItemSelectionCondition>
</ListItem>

```

<span data-ttu-id="5955f-119">項目の 1 つだけ選択条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5955f-119">You can specify only one selection condition for an item.</span></span> <span data-ttu-id="5955f-120">条件が 1 つのプロパティ名またはスクリプトを起動するトリガーの条件を指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="5955f-120">And the condition must specify one property name or script to trigger the condition, but cannot specify both.</span></span>

## <a name="xml-elements"></a><span data-ttu-id="5955f-121">XML 要素</span><span class="sxs-lookup"><span data-stu-id="5955f-121">XML Elements</span></span>

 <span data-ttu-id="5955f-122">次の XML 要素を使用して、選択条件を作成できます。</span><span class="sxs-lookup"><span data-stu-id="5955f-122">The following XML elements are used to create a selection condition.</span></span>

- <span data-ttu-id="5955f-123">次の要素は、ビュー定義の選択条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="5955f-123">The following elements specify selection conditions for view definitions:</span></span>

    - [<span data-ttu-id="5955f-124">TableControl (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="5955f-124">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

    - [<span data-ttu-id="5955f-125">ListControl (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="5955f-125">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

    - [<span data-ttu-id="5955f-126">WideControl (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="5955f-126">SelectionCondition Element for EntrySelectedBy for WideControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

    - [<span data-ttu-id="5955f-127">カスタム コントロール (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="5955f-127">SelectionCondition Element for EntrySelectedBy for CustomControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

- <span data-ttu-id="5955f-128">次の要素の選択範囲を指定する共通の条件とビューの定義を制御します。</span><span class="sxs-lookup"><span data-stu-id="5955f-128">The following elements specify selection conditions for common and view control definitions:</span></span>

    - [<span data-ttu-id="5955f-129">構成 (形式) のコントロールの EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="5955f-129">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

    - [<span data-ttu-id="5955f-130">コントロールが表示されます (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="5955f-130">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

- <span data-ttu-id="5955f-131">次の要素は、コレクション オブジェクトの拡張の選択条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="5955f-131">The following element specifies the selection condition for expanding collection objects:</span></span>

    - [<span data-ttu-id="5955f-132">EnumerableExpansion (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="5955f-132">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

- <span data-ttu-id="5955f-133">次の要素は、データの新しいグループを表示するための選択条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="5955f-133">The following element specifies the selection condition for displaying a new group of data:</span></span>

    - [<span data-ttu-id="5955f-134">GroupBy (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="5955f-134">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

- <span data-ttu-id="5955f-135">次の要素では、リスト ビューの項目の選択条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="5955f-135">The following element specifies an item selection condition for a list view:</span></span>

    - [<span data-ttu-id="5955f-136">ItemSelectionCondition ListControl (形式) を ListItem 要素</span><span class="sxs-lookup"><span data-stu-id="5955f-136">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

- <span data-ttu-id="5955f-137">次の要素では、コントロールの項目の選択条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="5955f-137">The following elements specify an item selection condition for controls:</span></span>

    - [<span data-ttu-id="5955f-138">ExpressionBinding の構成 (形式) のコントロールの ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="5955f-138">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

    - [<span data-ttu-id="5955f-139">コントロールが表示されます (形式) の ExpressionBinding ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="5955f-139">ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

    - [<span data-ttu-id="5955f-140">カスタム コントロール (形式) の ExpressionBinding ItemSelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="5955f-140">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

## <a name="see-also"></a><span data-ttu-id="5955f-141">参照</span><span class="sxs-lookup"><span data-stu-id="5955f-141">See Also</span></span>

[<span data-ttu-id="5955f-142">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="5955f-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
