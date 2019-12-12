---
title: ビュー (Format) のコントロールに対する CustomEntry の EntrySelectedBy 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3d80a7d-3797-4c46-ae74-ae5cda79b24f
caps.latest.revision: 8
ms.openlocfilehash: efb20c3f2077547e6eb3cb28240512b444f9c481
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363891"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-view-format"></a><span data-ttu-id="d1714-102">View の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d1714-102">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>

<span data-ttu-id="d1714-103">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="d1714-103">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="d1714-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d1714-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="d1714-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールの要素 (書式) コントロールのコントロール要素を表示するためのコントロール (format) の CustomControl 要素のコントロール要素ビューのための CustomControl (format) CustomEntry 要素のコントロール用のカスタムエントリのためのコントロールのためのコントロールのための、CustomEntry for Controls for コントロールの EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="d1714-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d1714-106">構文</span><span class="sxs-lookup"><span data-stu-id="d1714-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d1714-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="d1714-107">Attributes and Elements</span></span>

<span data-ttu-id="d1714-108">次のセクションでは、`EntrySelectedBy` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1714-108">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="d1714-109">定義には、少なくとも1つの種類、選択セット、または選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1714-109">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="d1714-110">使用できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="d1714-110">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="d1714-111">属性</span><span class="sxs-lookup"><span data-stu-id="d1714-111">Attributes</span></span>

<span data-ttu-id="d1714-112">なし。</span><span class="sxs-lookup"><span data-stu-id="d1714-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d1714-113">子要素</span><span class="sxs-lookup"><span data-stu-id="d1714-113">Child Elements</span></span>

|<span data-ttu-id="d1714-114">要素</span><span class="sxs-lookup"><span data-stu-id="d1714-114">Element</span></span>|<span data-ttu-id="d1714-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="d1714-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d1714-116">ビューのコントロール (Format) に対する EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="d1714-116">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="d1714-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d1714-117">Optional element.</span></span><br /><br /> <span data-ttu-id="d1714-118">この定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="d1714-118">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="d1714-119">ビューのコントロール (Format) の EntrySelectedBy の SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="d1714-119">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="d1714-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d1714-120">Optional element.</span></span><br /><br /> <span data-ttu-id="d1714-121">コントロールのこの定義を使用する .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="d1714-121">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="d1714-122">ビューのコントロール (Format) の EntrySelectedBy の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="d1714-122">TypeName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="d1714-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d1714-123">Optional element.</span></span><br /><br /> <span data-ttu-id="d1714-124">コントロールのこの定義を使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1714-124">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d1714-125">親要素</span><span class="sxs-lookup"><span data-stu-id="d1714-125">Parent Elements</span></span>

|<span data-ttu-id="d1714-126">要素</span><span class="sxs-lookup"><span data-stu-id="d1714-126">Element</span></span>|<span data-ttu-id="d1714-127">[説明]</span><span class="sxs-lookup"><span data-stu-id="d1714-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d1714-128">ビューのコントロール (Format) の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="d1714-128">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="d1714-129">コントロールの定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="d1714-129">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d1714-130">コメント</span><span class="sxs-lookup"><span data-stu-id="d1714-130">Remarks</span></span>

<span data-ttu-id="d1714-131">選択条件を使用して、オブジェクトに特定のプロパティがある場合や、特定のプロパティ値またはスクリプトが `true`に評価される場合など、使用する定義に必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="d1714-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="d1714-132">選択条件の詳細については、「[ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1714-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d1714-133">参照</span><span class="sxs-lookup"><span data-stu-id="d1714-133">See Also</span></span>

[<span data-ttu-id="d1714-134">ビューのコントロール (Format) の CustomEntry 要素</span><span class="sxs-lookup"><span data-stu-id="d1714-134">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="d1714-135">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="d1714-135">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
