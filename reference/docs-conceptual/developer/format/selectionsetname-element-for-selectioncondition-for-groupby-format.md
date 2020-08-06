---
title: GroupBy (Format) の SelectionCondition の SelectionSetName 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 6d0263aa335287f20be5b94a8eb65696d06d82a8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772622"
---
# <a name="selectionsetname-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="84595-102">GroupBy の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="84595-102">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="84595-103">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="84595-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="84595-104">このセット内のいずれかの型が存在する場合、条件が満たされ、このコントロールを使用してオブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="84595-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this control.</span></span> <span data-ttu-id="84595-105">この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="84595-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="84595-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素を groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素 CustomControl for groupby (Format) の CustomEntry for groupby (format) Selectionselectedby 要素の EntrySelectedBy を使用して groupby (format) SelectionSetName 要素を指定して、GroupBy (形式) の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="84595-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="84595-107">構文</span><span class="sxs-lookup"><span data-stu-id="84595-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="84595-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="84595-108">Attributes and Elements</span></span>

<span data-ttu-id="84595-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="84595-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="84595-110">属性</span><span class="sxs-lookup"><span data-stu-id="84595-110">Attributes</span></span>

<span data-ttu-id="84595-111">なし。</span><span class="sxs-lookup"><span data-stu-id="84595-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="84595-112">子要素</span><span class="sxs-lookup"><span data-stu-id="84595-112">Child Elements</span></span>

<span data-ttu-id="84595-113">なし。</span><span class="sxs-lookup"><span data-stu-id="84595-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="84595-114">親要素</span><span class="sxs-lookup"><span data-stu-id="84595-114">Parent Elements</span></span>

|<span data-ttu-id="84595-115">要素</span><span class="sxs-lookup"><span data-stu-id="84595-115">Element</span></span>|<span data-ttu-id="84595-116">説明</span><span class="sxs-lookup"><span data-stu-id="84595-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="84595-117">GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="84595-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="84595-118">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="84595-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="84595-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="84595-119">Text Value</span></span>

<span data-ttu-id="84595-120">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="84595-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="84595-121">解説</span><span class="sxs-lookup"><span data-stu-id="84595-121">Remarks</span></span>

<span data-ttu-id="84595-122">選択セットは、書式設定ファイルによって定義される任意のビューで使用できる .NET オブジェクトの一般的なグループです。</span><span class="sxs-lookup"><span data-stu-id="84595-122">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="84595-123">選択セットの作成と参照の詳細については、「[選択セットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84595-123">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="84595-124">この要素が指定されている場合、 [TypeName](./typename-element-for-selectioncondition-for-groupby-format.md)要素を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="84595-124">When this element is specified, you cannot specify the [TypeName](./typename-element-for-selectioncondition-for-groupby-format.md) element.</span></span> <span data-ttu-id="84595-125">選択条件の定義の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84595-125">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="84595-126">参照</span><span class="sxs-lookup"><span data-stu-id="84595-126">See Also</span></span>

[<span data-ttu-id="84595-127">GroupBy の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="84595-127">TypeName Element for SelectionCondition for GroupBy (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="84595-128">GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="84595-128">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="84595-129">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="84595-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="84595-130">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="84595-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="84595-131">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="84595-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
