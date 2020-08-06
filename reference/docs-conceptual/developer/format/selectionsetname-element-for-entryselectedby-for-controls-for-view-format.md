---
title: ビュー (Format) のコントロールに対する EntrySelectedBy の SelectionSetName 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 5c762a626fff746266919d1f7fcb991a8cdbcdf2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787548"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="e9980-102">View の Controls の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e9980-102">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="e9980-103">コントロールのこの定義を使用する .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="e9980-103">Specifies a set of .NET types that use this definition of the control.</span></span> <span data-ttu-id="e9980-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e9980-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="e9980-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールのコントロールの要素 (書式) コントロールのコントロール要素 (format) コントロールの要素 (書式) コントロールの要素 (書式) をコントロールに対して、ビュー (Format) の CustomControl の CustomControl 要素 for view (format) CustomEntry 要素に対して、CustomEntry の EntrySelectedBy 要素を使用して、ビュー (Format) のコントロールに対して EntrySelectedBy の SelectionSetName 要素を表示 (format)</span><span class="sxs-lookup"><span data-stu-id="e9980-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e9980-106">構文</span><span class="sxs-lookup"><span data-stu-id="e9980-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="e9980-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e9980-107">Attributes and Elements</span></span>

<span data-ttu-id="e9980-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="e9980-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e9980-109">属性</span><span class="sxs-lookup"><span data-stu-id="e9980-109">Attributes</span></span>

<span data-ttu-id="e9980-110">なし</span><span class="sxs-lookup"><span data-stu-id="e9980-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="e9980-111">子要素</span><span class="sxs-lookup"><span data-stu-id="e9980-111">Child Elements</span></span>

<span data-ttu-id="e9980-112">なし。</span><span class="sxs-lookup"><span data-stu-id="e9980-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e9980-113">親要素</span><span class="sxs-lookup"><span data-stu-id="e9980-113">Parent Elements</span></span>

|<span data-ttu-id="e9980-114">要素</span><span class="sxs-lookup"><span data-stu-id="e9980-114">Element</span></span>|<span data-ttu-id="e9980-115">説明</span><span class="sxs-lookup"><span data-stu-id="e9980-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e9980-116">View の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e9980-116">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="e9980-117">このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="e9980-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e9980-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="e9980-118">Text Value</span></span>

<span data-ttu-id="e9980-119">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e9980-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="e9980-120">解説</span><span class="sxs-lookup"><span data-stu-id="e9980-120">Remarks</span></span>

<span data-ttu-id="e9980-121">各コントロール定義には、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9980-121">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="e9980-122">選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="e9980-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="e9980-123">選択セットの定義の詳細については、「[選択セットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9980-123">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e9980-124">参照</span><span class="sxs-lookup"><span data-stu-id="e9980-124">See Also</span></span>

[<span data-ttu-id="e9980-125">View の Controls の CustomEntry の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e9980-125">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="e9980-126">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="e9980-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
