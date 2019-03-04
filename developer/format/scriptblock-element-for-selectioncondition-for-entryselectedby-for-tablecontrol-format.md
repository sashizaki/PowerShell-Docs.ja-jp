---
title: TableControl (形式) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b11fbcf-3426-48ae-9319-2c847969f723
caps.latest.revision: 10
ms.openlocfilehash: 7afc834e68ef332bee1e23da782fb5c5527fcf54
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855578"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="b8ccb-102">TableControl の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b8ccb-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="b8ccb-103">条件をトリガーするスクリプト ブロックを指定します。</span><span class="sxs-lookup"><span data-stu-id="b8ccb-103">Specifies the script block that triggers the condition.</span></span> <span data-ttu-id="b8ccb-104">このスクリプトを評価するときに`true`条件が満たされると、およびテーブル エントリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b8ccb-104">When this script is evaluated to `true`, the condition is met, and the table entry is used.</span></span>

<span data-ttu-id="b8ccb-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableRowEntries 要素 (形式) TableRowEntry 要素 (形式) EntrySelectedBy 要素を TableRowEntry (形式)SelectionCondition EntrySelectedBy TableRowEntry (形式) のための TableRowEntry (形式) ScriptBlock 要素 EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="b8ccb-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b8ccb-106">構文</span><span class="sxs-lookup"><span data-stu-id="b8ccb-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b8ccb-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="b8ccb-107">Attributes and Elements</span></span>

<span data-ttu-id="b8ccb-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`ScriptBlock`要素。</span><span class="sxs-lookup"><span data-stu-id="b8ccb-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b8ccb-109">属性</span><span class="sxs-lookup"><span data-stu-id="b8ccb-109">Attributes</span></span>

<span data-ttu-id="b8ccb-110">なし。</span><span class="sxs-lookup"><span data-stu-id="b8ccb-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b8ccb-111">子要素</span><span class="sxs-lookup"><span data-stu-id="b8ccb-111">Child Elements</span></span>

<span data-ttu-id="b8ccb-112">なし。</span><span class="sxs-lookup"><span data-stu-id="b8ccb-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b8ccb-113">親要素</span><span class="sxs-lookup"><span data-stu-id="b8ccb-113">Parent Elements</span></span>

|<span data-ttu-id="b8ccb-114">要素</span><span class="sxs-lookup"><span data-stu-id="b8ccb-114">Element</span></span>|<span data-ttu-id="b8ccb-115">説明</span><span class="sxs-lookup"><span data-stu-id="b8ccb-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b8ccb-116">TableRowEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="b8ccb-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="b8ccb-117">このテーブルのエントリを使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="b8ccb-117">Defines the condition that must exist for this table entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b8ccb-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="b8ccb-118">Text Value</span></span>

<span data-ttu-id="b8ccb-119">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="b8ccb-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="b8ccb-120">コメント</span><span class="sxs-lookup"><span data-stu-id="b8ccb-120">Remarks</span></span>

<span data-ttu-id="b8ccb-121">選択条件では、少なくとも 1 つのスクリプト ブロックまたはプロパティの名前を指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="b8ccb-121">The selection condition must specify at least one script block or property name, but cannot specify both.</span></span> <span data-ttu-id="b8ccb-122">選択条件を使用する方法の詳細については、次を参照してください。[とビューのエントリの定義の条件またはアイテムが使用されて](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="b8ccb-122">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="b8ccb-123">テーブル ビューのコンポーネントに関する詳細については、次を参照してください。[テーブル ビューを作成する](./creating-a-table-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="b8ccb-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b8ccb-124">参照</span><span class="sxs-lookup"><span data-stu-id="b8ccb-124">See Also</span></span>

[<span data-ttu-id="b8ccb-125">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="b8ccb-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="b8ccb-126">データが表示される場合の条件の定義</span><span class="sxs-lookup"><span data-stu-id="b8ccb-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="b8ccb-127">SelectionCondition EntrySelectedBy TableRowEntry (形式) のための PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="b8ccb-127">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[<span data-ttu-id="b8ccb-128">TableRowEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="b8ccb-128">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="b8ccb-129">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="b8ccb-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
