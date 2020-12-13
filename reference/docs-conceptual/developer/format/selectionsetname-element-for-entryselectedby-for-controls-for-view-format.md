---
ms.date: 09/13/2016
ms.topic: reference
title: View の Controls の EntrySelectedBy の SelectionSetName 要素 (書式)
description: View の Controls の EntrySelectedBy の SelectionSetName 要素 (書式)
ms.openlocfilehash: 3211b7cacd7e57770b48b03f4aade33da506f180
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664731"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="d27b6-103">View の Controls の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d27b6-103">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="d27b6-104">コントロールのこの定義を使用する .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="d27b6-104">Specifies a set of .NET types that use this definition of the control.</span></span> <span data-ttu-id="d27b6-105">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d27b6-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="d27b6-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールのコントロールの要素 (書式) コントロールのコントロール要素 (format) コントロールの要素 (書式) コントロールの要素 (書式) をコントロールに対して、ビュー (Format) の CustomControl の CustomControl 要素 for view (format) CustomEntry 要素に対して、CustomEntry の EntrySelectedBy 要素を使用して、ビュー (Format) のコントロールに対して EntrySelectedBy の SelectionSetName 要素を表示 (format)</span><span class="sxs-lookup"><span data-stu-id="d27b6-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d27b6-107">構文</span><span class="sxs-lookup"><span data-stu-id="d27b6-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="d27b6-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d27b6-108">Attributes and Elements</span></span>

<span data-ttu-id="d27b6-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="d27b6-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d27b6-110">属性</span><span class="sxs-lookup"><span data-stu-id="d27b6-110">Attributes</span></span>

<span data-ttu-id="d27b6-111">なし</span><span class="sxs-lookup"><span data-stu-id="d27b6-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="d27b6-112">子要素</span><span class="sxs-lookup"><span data-stu-id="d27b6-112">Child Elements</span></span>

<span data-ttu-id="d27b6-113">なし。</span><span class="sxs-lookup"><span data-stu-id="d27b6-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d27b6-114">親要素</span><span class="sxs-lookup"><span data-stu-id="d27b6-114">Parent Elements</span></span>

|<span data-ttu-id="d27b6-115">要素</span><span class="sxs-lookup"><span data-stu-id="d27b6-115">Element</span></span>|<span data-ttu-id="d27b6-116">説明</span><span class="sxs-lookup"><span data-stu-id="d27b6-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d27b6-117">View の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d27b6-117">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="d27b6-118">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="d27b6-118">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d27b6-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="d27b6-119">Text Value</span></span>

<span data-ttu-id="d27b6-120">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d27b6-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="d27b6-121">解説</span><span class="sxs-lookup"><span data-stu-id="d27b6-121">Remarks</span></span>

<span data-ttu-id="d27b6-122">各コントロール定義には、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d27b6-122">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="d27b6-123">選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="d27b6-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="d27b6-124">選択セットの定義の詳細については、「 [選択セットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d27b6-124">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d27b6-125">参照</span><span class="sxs-lookup"><span data-stu-id="d27b6-125">See Also</span></span>

[<span data-ttu-id="d27b6-126">View の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d27b6-126">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="d27b6-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="d27b6-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
