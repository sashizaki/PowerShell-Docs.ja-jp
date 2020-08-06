---
title: ビューのコントロールの SelectionCondition の SelectionSetName 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 0feb23f860487952344680f75ee674e9e0e6dcc6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787531"
---
# <a name="selectionsetname-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="a0b7a-102">View の Controls の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a0b7a-102">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="a0b7a-103">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="a0b7a-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="a0b7a-104">このセット内のいずれかの型が存在する場合、条件が満たされ、このコントロールを使用してオブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0b7a-104">When any of the types in this set are present, the condition is met and the object is displayed using this control.</span></span> <span data-ttu-id="a0b7a-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a0b7a-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="a0b7a-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールのコントロールの要素 (形式) コントロールのコントロール要素 (format) のコントロールの要素 (書式) を制御するためのコントロールの要素 (書式) の CustomControl 要素 (format) のコントロールの CustomControl のカスタム CustomEntries ビュー (format) のためのコントロールの CustomEntries の参照 (format) の参照 (format) の SelectionCondition 要素を表示するためのコントロールのための SelectionSetName 要素の参照 (format) の selectioncondition 要素を表示するためのコントロールの参照 (format) 要素</span><span class="sxs-lookup"><span data-stu-id="a0b7a-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a0b7a-107">構文</span><span class="sxs-lookup"><span data-stu-id="a0b7a-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a0b7a-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a0b7a-108">Attributes and Elements</span></span>

<span data-ttu-id="a0b7a-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="a0b7a-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a0b7a-110">属性</span><span class="sxs-lookup"><span data-stu-id="a0b7a-110">Attributes</span></span>

<span data-ttu-id="a0b7a-111">なし。</span><span class="sxs-lookup"><span data-stu-id="a0b7a-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a0b7a-112">子要素</span><span class="sxs-lookup"><span data-stu-id="a0b7a-112">Child Elements</span></span>

<span data-ttu-id="a0b7a-113">なし。</span><span class="sxs-lookup"><span data-stu-id="a0b7a-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a0b7a-114">親要素</span><span class="sxs-lookup"><span data-stu-id="a0b7a-114">Parent Elements</span></span>

|<span data-ttu-id="a0b7a-115">要素</span><span class="sxs-lookup"><span data-stu-id="a0b7a-115">Element</span></span>|<span data-ttu-id="a0b7a-116">説明</span><span class="sxs-lookup"><span data-stu-id="a0b7a-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a0b7a-117">View の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a0b7a-117">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="a0b7a-118">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="a0b7a-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a0b7a-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="a0b7a-119">Text Value</span></span>

<span data-ttu-id="a0b7a-120">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a0b7a-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="a0b7a-121">解説</span><span class="sxs-lookup"><span data-stu-id="a0b7a-121">Remarks</span></span>

<span data-ttu-id="a0b7a-122">選択セットは、書式設定ファイルによって定義される任意のビューで使用できる .NET オブジェクトの一般的なグループです。</span><span class="sxs-lookup"><span data-stu-id="a0b7a-122">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="a0b7a-123">選択セットの作成と参照の詳細については、「[選択セットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0b7a-123">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="a0b7a-124">選択条件では、選択セットまたは .NET 型を指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="a0b7a-124">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="a0b7a-125">選択条件の使用方法の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0b7a-125">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a0b7a-126">参照</span><span class="sxs-lookup"><span data-stu-id="a0b7a-126">See Also</span></span>

[<span data-ttu-id="a0b7a-127">View の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a0b7a-127">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="a0b7a-128">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="a0b7a-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="a0b7a-129">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="a0b7a-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="a0b7a-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="a0b7a-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
