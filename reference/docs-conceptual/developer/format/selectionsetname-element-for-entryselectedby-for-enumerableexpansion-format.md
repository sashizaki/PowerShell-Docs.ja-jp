---
ms.date: 09/13/2016
ms.topic: reference
title: EnumerableExpansion の EntrySelectedBy の SelectionSetName 要素 (書式)
description: EnumerableExpansion の EntrySelectedBy の SelectionSetName 要素 (書式)
ms.openlocfilehash: 074f810f5a3cbad61ee8be69408967758f0591df
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651875"
---
# <a name="selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="b36b7-103">EnumerableExpansion の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b36b7-103">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="b36b7-104">この定義によって展開される .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="b36b7-104">Specifies the set of .NET types that are expanded by this definition.</span></span>

<span data-ttu-id="b36b7-105">Configuration 要素 (Format) DefaultSettings 要素 (format) enumerableexpansions 要素 (format) 列挙 able膨張拡張要素 (format) の entryselectedby (format) SelectionSetName 要素 (format Able膨張の場合は Format) のエントリを列挙します。</span><span class="sxs-lookup"><span data-stu-id="b36b7-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b36b7-106">構文</span><span class="sxs-lookup"><span data-stu-id="b36b7-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="b36b7-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b36b7-107">Attributes and Elements</span></span>

<span data-ttu-id="b36b7-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="b36b7-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b36b7-109">属性</span><span class="sxs-lookup"><span data-stu-id="b36b7-109">Attributes</span></span>

<span data-ttu-id="b36b7-110">なし。</span><span class="sxs-lookup"><span data-stu-id="b36b7-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b36b7-111">子要素</span><span class="sxs-lookup"><span data-stu-id="b36b7-111">Child Elements</span></span>

<span data-ttu-id="b36b7-112">なし。</span><span class="sxs-lookup"><span data-stu-id="b36b7-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b36b7-113">親要素</span><span class="sxs-lookup"><span data-stu-id="b36b7-113">Parent Elements</span></span>

|<span data-ttu-id="b36b7-114">要素</span><span class="sxs-lookup"><span data-stu-id="b36b7-114">Element</span></span>|<span data-ttu-id="b36b7-115">説明</span><span class="sxs-lookup"><span data-stu-id="b36b7-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b36b7-116">EnumerableExpansion の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b36b7-116">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="b36b7-117">この定義によって展開される .NET コレクションオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="b36b7-117">Defines the .NET collection objects that are expanded by this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b36b7-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="b36b7-118">Text Value</span></span>

<span data-ttu-id="b36b7-119">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b36b7-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="b36b7-120">解説</span><span class="sxs-lookup"><span data-stu-id="b36b7-120">Remarks</span></span>

<span data-ttu-id="b36b7-121">各定義には、1つ以上の型名、選択セット、または選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b36b7-121">Each definition must specify one or more type names, a selection set, or a selection condition.</span></span>

<span data-ttu-id="b36b7-122">選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="b36b7-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="b36b7-123">たとえば、同じオブジェクトのセットに対してテーブルビューとリストビューを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="b36b7-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="b36b7-124">選択セットの定義の詳細については、「 [ビューのオブジェクトセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b36b7-124">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b36b7-125">参照</span><span class="sxs-lookup"><span data-stu-id="b36b7-125">See Also</span></span>

[<span data-ttu-id="b36b7-126">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="b36b7-126">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="b36b7-127">EnumerableExpansion の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="b36b7-127">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)

[<span data-ttu-id="b36b7-128">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="b36b7-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
