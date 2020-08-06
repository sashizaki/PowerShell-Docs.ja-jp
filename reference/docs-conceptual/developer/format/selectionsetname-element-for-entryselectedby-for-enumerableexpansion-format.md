---
title: 列挙 Able膨張 (Format) の EntrySelectedBy の SelectionSetName 要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 8745ef9e6f326c3e8a5dbf185a595bbe93e92414
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785321"
---
# <a name="selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="bcea0-102">EnumerableExpansion の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bcea0-102">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="bcea0-103">この定義によって展開される .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="bcea0-103">Specifies the set of .NET types that are expanded by this definition.</span></span>

<span data-ttu-id="bcea0-104">Configuration 要素 (Format) DefaultSettings 要素 (format) enumerableexpansions 要素 (format) 列挙 able膨張拡張要素 (format) の entryselectedby (format) SelectionSetName 要素 (format Able膨張の場合は Format) のエントリを列挙します。</span><span class="sxs-lookup"><span data-stu-id="bcea0-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bcea0-105">構文</span><span class="sxs-lookup"><span data-stu-id="bcea0-105">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="bcea0-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="bcea0-106">Attributes and Elements</span></span>

<span data-ttu-id="bcea0-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="bcea0-107">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bcea0-108">属性</span><span class="sxs-lookup"><span data-stu-id="bcea0-108">Attributes</span></span>

<span data-ttu-id="bcea0-109">なし。</span><span class="sxs-lookup"><span data-stu-id="bcea0-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bcea0-110">子要素</span><span class="sxs-lookup"><span data-stu-id="bcea0-110">Child Elements</span></span>

<span data-ttu-id="bcea0-111">なし。</span><span class="sxs-lookup"><span data-stu-id="bcea0-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="bcea0-112">親要素</span><span class="sxs-lookup"><span data-stu-id="bcea0-112">Parent Elements</span></span>

|<span data-ttu-id="bcea0-113">要素</span><span class="sxs-lookup"><span data-stu-id="bcea0-113">Element</span></span>|<span data-ttu-id="bcea0-114">説明</span><span class="sxs-lookup"><span data-stu-id="bcea0-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bcea0-115">EnumerableExpansion の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bcea0-115">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="bcea0-116">この定義によって展開される .NET コレクションオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="bcea0-116">Defines the .NET collection objects that are expanded by this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="bcea0-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="bcea0-117">Text Value</span></span>

<span data-ttu-id="bcea0-118">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="bcea0-118">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="bcea0-119">解説</span><span class="sxs-lookup"><span data-stu-id="bcea0-119">Remarks</span></span>

<span data-ttu-id="bcea0-120">各定義には、1つ以上の型名、選択セット、または選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcea0-120">Each definition must specify one or more type names, a selection set, or a selection condition.</span></span>

<span data-ttu-id="bcea0-121">選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="bcea0-121">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="bcea0-122">たとえば、同じオブジェクトのセットに対してテーブルビューとリストビューを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="bcea0-122">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="bcea0-123">選択セットの定義の詳細については、「[ビューのオブジェクトセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcea0-123">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bcea0-124">参照</span><span class="sxs-lookup"><span data-stu-id="bcea0-124">See Also</span></span>

[<span data-ttu-id="bcea0-125">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="bcea0-125">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="bcea0-126">EnumerableExpansion の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="bcea0-126">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)

[<span data-ttu-id="bcea0-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="bcea0-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
