---
title: コントロールが表示されます (形式) の SelectionCondition SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: daea8c6f-873a-4639-9eee-599642822958
caps.latest.revision: 6
ms.openlocfilehash: 697f2ea284393ebddd77a862c408f27f3d332900
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855118"
---
# <a name="selectionsetname-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="b0a7c-102">View の Controls の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b0a7c-102">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="b0a7c-103">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0a7c-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="b0a7c-104">このセット内の型のいずれかが存在するときに、条件が満たされ、このコントロールを使用して、オブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0a7c-104">When any of the types in this set are present, the condition is met and the object is displayed using this control.</span></span> <span data-ttu-id="b0a7c-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0a7c-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="b0a7c-106">要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式) コントロール要素 (形式) コントロールの構成要素のビュー (形式) CustomEntries 要素のコントロールのコントロールのビュー (形式) のカスタム コントロール要素のコントロールCustomEntries CustomEntry EntrySelectedBy のビュー (コントロールのビュー (形式) SelectionCondition 要素のコントロールのビュー (形式) EntrySelectedBy 要素のコントロールのビュー (形式) CustomEntry 要素のコントロールのカスタム コントロールコントロールが表示されます (形式) の SelectionCondition の形式) SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="b0a7c-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b0a7c-107">構文</span><span class="sxs-lookup"><span data-stu-id="b0a7c-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b0a7c-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="b0a7c-108">Attributes and Elements</span></span>

<span data-ttu-id="b0a7c-109">次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionSetName`要素。</span><span class="sxs-lookup"><span data-stu-id="b0a7c-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b0a7c-110">属性</span><span class="sxs-lookup"><span data-stu-id="b0a7c-110">Attributes</span></span>

<span data-ttu-id="b0a7c-111">なし。</span><span class="sxs-lookup"><span data-stu-id="b0a7c-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b0a7c-112">子要素</span><span class="sxs-lookup"><span data-stu-id="b0a7c-112">Child Elements</span></span>

<span data-ttu-id="b0a7c-113">なし。</span><span class="sxs-lookup"><span data-stu-id="b0a7c-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b0a7c-114">親要素</span><span class="sxs-lookup"><span data-stu-id="b0a7c-114">Parent Elements</span></span>

|<span data-ttu-id="b0a7c-115">要素</span><span class="sxs-lookup"><span data-stu-id="b0a7c-115">Element</span></span>|<span data-ttu-id="b0a7c-116">説明</span><span class="sxs-lookup"><span data-stu-id="b0a7c-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b0a7c-117">コントロールが表示されます (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="b0a7c-117">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="b0a7c-118">コントロールの定義を使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="b0a7c-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b0a7c-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="b0a7c-119">Text Value</span></span>

<span data-ttu-id="b0a7c-120">選択範囲のセットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0a7c-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="b0a7c-121">コメント</span><span class="sxs-lookup"><span data-stu-id="b0a7c-121">Remarks</span></span>

<span data-ttu-id="b0a7c-122">選択範囲のセットは、書式設定ファイルを定義する任意のビューで使用できる .NET オブジェクトの一般的なグループです。</span><span class="sxs-lookup"><span data-stu-id="b0a7c-122">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="b0a7c-123">作成と選択範囲のセットの参照の詳細については、次を参照してください。[選択範囲の設定を定義する](./defining-selection-sets.md)します。</span><span class="sxs-lookup"><span data-stu-id="b0a7c-123">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="b0a7c-124">選択条件では、選択範囲のセットまたは .NET の型を指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="b0a7c-124">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="b0a7c-125">選択条件を使用する方法の詳細については、次を参照してください。[を表示するデータの条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="b0a7c-125">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b0a7c-126">参照</span><span class="sxs-lookup"><span data-stu-id="b0a7c-126">See Also</span></span>

[<span data-ttu-id="b0a7c-127">コントロールが表示されます (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="b0a7c-127">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="b0a7c-128">データが表示される場合の条件の定義</span><span class="sxs-lookup"><span data-stu-id="b0a7c-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="b0a7c-129">選択範囲のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="b0a7c-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="b0a7c-130">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="b0a7c-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
