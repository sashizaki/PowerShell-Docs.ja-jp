---
ms.date: 09/13/2016
ms.topic: reference
title: View の CustomControl の SelectionCondition の SelectionSetName 要素 (書式)
description: View の CustomControl の SelectionCondition の SelectionSetName 要素 (書式)
ms.openlocfilehash: 839032048739e529057d7066fb3bc6aa2fbc5037
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651609"
---
# <a name="selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="ab6bf-103">View の CustomControl の SelectionCondition の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ab6bf-103">SelectionSetName Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="ab6bf-104">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab6bf-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="ab6bf-105">このセット内のいずれかの型が存在する場合、条件が満たされ、このコントロールを使用してオブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab6bf-105">When any of the types in this set are present, the condition is met and the object is displayed using this control.</span></span> <span data-ttu-id="ab6bf-106">この要素は、カスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ab6bf-106">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="ab6bf-107">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) CustomControl 要素 (形式) の CustomEntries for CustomControl for view (format) の CustomEntry 要素を使用して、CustomEntry for ビューの EntrySelectedBy 要素を表示 (形式) します。</span><span class="sxs-lookup"><span data-stu-id="ab6bf-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ab6bf-108">構文</span><span class="sxs-lookup"><span data-stu-id="ab6bf-108">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ab6bf-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ab6bf-109">Attributes and Elements</span></span>

<span data-ttu-id="ab6bf-110">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="ab6bf-110">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ab6bf-111">属性</span><span class="sxs-lookup"><span data-stu-id="ab6bf-111">Attributes</span></span>

<span data-ttu-id="ab6bf-112">なし。</span><span class="sxs-lookup"><span data-stu-id="ab6bf-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ab6bf-113">子要素</span><span class="sxs-lookup"><span data-stu-id="ab6bf-113">Child Elements</span></span>

<span data-ttu-id="ab6bf-114">なし。</span><span class="sxs-lookup"><span data-stu-id="ab6bf-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ab6bf-115">親要素</span><span class="sxs-lookup"><span data-stu-id="ab6bf-115">Parent Elements</span></span>

|<span data-ttu-id="ab6bf-116">要素</span><span class="sxs-lookup"><span data-stu-id="ab6bf-116">Element</span></span>|<span data-ttu-id="ab6bf-117">説明</span><span class="sxs-lookup"><span data-stu-id="ab6bf-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ab6bf-118">CustomControl for ビュー (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="ab6bf-118">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="ab6bf-119">コントロール定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="ab6bf-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ab6bf-120">テキスト値</span><span class="sxs-lookup"><span data-stu-id="ab6bf-120">Text Value</span></span>

<span data-ttu-id="ab6bf-121">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab6bf-121">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="ab6bf-122">解説</span><span class="sxs-lookup"><span data-stu-id="ab6bf-122">Remarks</span></span>

<span data-ttu-id="ab6bf-123">選択セットは、書式設定ファイルによって定義される任意のビューで使用できる .NET オブジェクトの一般的なグループです。</span><span class="sxs-lookup"><span data-stu-id="ab6bf-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="ab6bf-124">選択セットの作成と参照の詳細については、「 [オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab6bf-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="ab6bf-125">選択条件では、選択セットまたは .NET 型を指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="ab6bf-125">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="ab6bf-126">選択条件の使用方法の詳細については、「 [データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab6bf-126">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ab6bf-127">参照</span><span class="sxs-lookup"><span data-stu-id="ab6bf-127">See Also</span></span>

[<span data-ttu-id="ab6bf-128">CustomControl for ビュー (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="ab6bf-128">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="ab6bf-129">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="ab6bf-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="ab6bf-130">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="ab6bf-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="ab6bf-131">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="ab6bf-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
