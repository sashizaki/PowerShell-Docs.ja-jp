---
title: GroupBy (Format) の SelectionCondition の SelectionSetName 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b9a4912-d755-42f3-8058-53c0797e28e4
caps.latest.revision: 6
ms.openlocfilehash: 371913eda2b09ff6788494b68738f2ad53ccb115
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361861"
---
# <a name="selectionsetname-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="2f2cf-102">GroupBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="2f2cf-102">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="2f2cf-103">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="2f2cf-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="2f2cf-104">このセット内のいずれかの型が存在する場合、条件が満たされ、このコントロールを使用してオブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f2cf-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this control.</span></span> <span data-ttu-id="2f2cf-105">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="2f2cf-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="2f2cf-106">Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素の groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素Groupby (format) の CustomControl の Entryselectedby for groupby (format) Selectionselectedby 要素の Selectionselectedby を使用して groupby (format) SelectionSetName 要素を指定します。 groupby (形式) の SelectionCondition です。</span><span class="sxs-lookup"><span data-stu-id="2f2cf-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2f2cf-107">構文</span><span class="sxs-lookup"><span data-stu-id="2f2cf-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2f2cf-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="2f2cf-108">Attributes and Elements</span></span>

<span data-ttu-id="2f2cf-109">次のセクションでは、属性、子要素、`SelectionSetName` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2f2cf-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2f2cf-110">属性</span><span class="sxs-lookup"><span data-stu-id="2f2cf-110">Attributes</span></span>

<span data-ttu-id="2f2cf-111">なし。</span><span class="sxs-lookup"><span data-stu-id="2f2cf-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2f2cf-112">子要素</span><span class="sxs-lookup"><span data-stu-id="2f2cf-112">Child Elements</span></span>

<span data-ttu-id="2f2cf-113">なし。</span><span class="sxs-lookup"><span data-stu-id="2f2cf-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2f2cf-114">親要素</span><span class="sxs-lookup"><span data-stu-id="2f2cf-114">Parent Elements</span></span>

|<span data-ttu-id="2f2cf-115">要素</span><span class="sxs-lookup"><span data-stu-id="2f2cf-115">Element</span></span>|<span data-ttu-id="2f2cf-116">[説明]</span><span class="sxs-lookup"><span data-stu-id="2f2cf-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2f2cf-117">GroupBy (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="2f2cf-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="2f2cf-118">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="2f2cf-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2f2cf-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="2f2cf-119">Text Value</span></span>

<span data-ttu-id="2f2cf-120">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2f2cf-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="2f2cf-121">コメント</span><span class="sxs-lookup"><span data-stu-id="2f2cf-121">Remarks</span></span>

<span data-ttu-id="2f2cf-122">選択セットは、書式設定ファイルによって定義される任意のビューで使用できる .NET オブジェクトの一般的なグループです。</span><span class="sxs-lookup"><span data-stu-id="2f2cf-122">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="2f2cf-123">選択セットの作成と参照の詳細については、「[選択セットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f2cf-123">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="2f2cf-124">この要素が指定されている場合、 [TypeName](./typename-element-for-selectioncondition-for-groupby-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="2f2cf-124">When this element is specified, you cannot specify the [TypeName](./typename-element-for-selectioncondition-for-groupby-format.md) element.</span></span> <span data-ttu-id="2f2cf-125">選択条件の定義の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f2cf-125">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2f2cf-126">参照</span><span class="sxs-lookup"><span data-stu-id="2f2cf-126">See Also</span></span>

[<span data-ttu-id="2f2cf-127">GroupBy (Format) の SelectionCondition の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="2f2cf-127">TypeName Element for SelectionCondition for GroupBy (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="2f2cf-128">GroupBy (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="2f2cf-128">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="2f2cf-129">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="2f2cf-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="2f2cf-130">選択セットの定義</span><span class="sxs-lookup"><span data-stu-id="2f2cf-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="2f2cf-131">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="2f2cf-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
