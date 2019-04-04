---
title: TableControl (形式) の EntrySelectedBy の SelectionCondition の TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e97d56fb-4e35-447a-9282-26f10d0a4609
caps.latest.revision: 11
ms.openlocfilehash: fe65ac95cead7df0069ffdae666fb34b7309fbb6
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856498"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="b3f8d-102">TableControl の EntrySelectedBy の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b3f8d-102">TypeName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="b3f8d-103">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="b3f8d-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="b3f8d-104">この型が存在して、条件が満たされると、テーブルの行を使用します。</span><span class="sxs-lookup"><span data-stu-id="b3f8d-104">When this type is present, the condition is met, and the table row is used.</span></span>

<span data-ttu-id="b3f8d-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) TableControl 要素 (形式) TableRowEntries 要素 (形式) TableRowEntry 要素 (形式) EntrySelectedBy 要素を TableRowEntry (形式)SelectionCondition EntrySelectedBy TableRowEntry (形式) のための TableRowEntry (形式) の TypeName 要素 EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="b3f8d-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b3f8d-106">構文</span><span class="sxs-lookup"><span data-stu-id="b3f8d-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b3f8d-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="b3f8d-107">Attributes and Elements</span></span>

<span data-ttu-id="b3f8d-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`TypeName`要素。</span><span class="sxs-lookup"><span data-stu-id="b3f8d-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b3f8d-109">属性</span><span class="sxs-lookup"><span data-stu-id="b3f8d-109">Attributes</span></span>

<span data-ttu-id="b3f8d-110">なし。</span><span class="sxs-lookup"><span data-stu-id="b3f8d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b3f8d-111">子要素</span><span class="sxs-lookup"><span data-stu-id="b3f8d-111">Child Elements</span></span>

<span data-ttu-id="b3f8d-112">なし。</span><span class="sxs-lookup"><span data-stu-id="b3f8d-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b3f8d-113">親要素</span><span class="sxs-lookup"><span data-stu-id="b3f8d-113">Parent Elements</span></span>

|<span data-ttu-id="b3f8d-114">要素</span><span class="sxs-lookup"><span data-stu-id="b3f8d-114">Element</span></span>|<span data-ttu-id="b3f8d-115">説明</span><span class="sxs-lookup"><span data-stu-id="b3f8d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b3f8d-116">TableRowEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="b3f8d-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="b3f8d-117">このテーブルの行を使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="b3f8d-117">Defines the condition that must exist for this table row to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b3f8d-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="b3f8d-118">Text Value</span></span>

<span data-ttu-id="b3f8d-119">.NET 型の完全修飾名を指定します。`System.IO.DirectoryInfo`します。</span><span class="sxs-lookup"><span data-stu-id="b3f8d-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b3f8d-120">コメント</span><span class="sxs-lookup"><span data-stu-id="b3f8d-120">Remarks</span></span>

<span data-ttu-id="b3f8d-121">選択条件が .NET 型の任意の数を指定するか、選択範囲を設定するが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="b3f8d-121">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="b3f8d-122">選択条件を使用する方法の詳細については、[とビューのエントリの定義の条件またはアイテムが使用されて](./defining-conditions-for-displaying-data.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3f8d-122">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="b3f8d-123">テーブル ビューのコンポーネントに関する詳細については、[テーブル ビューを作成する](./creating-a-table-view.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3f8d-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b3f8d-124">参照</span><span class="sxs-lookup"><span data-stu-id="b3f8d-124">See Also</span></span>

[<span data-ttu-id="b3f8d-125">テーブル ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="b3f8d-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="b3f8d-126">データが表示される場合の条件の定義</span><span class="sxs-lookup"><span data-stu-id="b3f8d-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="b3f8d-127">TableRowEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="b3f8d-127">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="b3f8d-128">EntrySelectedBy TableRowEntry (形式) 用の SelectionCondition SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="b3f8d-128">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="b3f8d-129">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="b3f8d-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
