---
title: 列挙 Able膨張 (Format) の EntrySelectedBy の SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 936d09f2-2c48-49e8-ab2d-0c8729199a2e
caps.latest.revision: 8
ms.openlocfilehash: 8ba8931ea5e34f610878351396cad42023393ad6
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368331"
---
# <a name="selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="c2fac-102">EnumerableExpansion の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="c2fac-102">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="c2fac-103">この定義によって展開される .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="c2fac-103">Specifies the set of .NET types that are expanded by this definition.</span></span>

<span data-ttu-id="c2fac-104">Configuration 要素 (Format) DefaultSettings 要素 (format) には、EntrySelectedBy 要素 (format) の entryselectedby 要素 (format) を指定します。この場合、EntrySelectedBy の SelectionSetName 要素を指定します。列挙 Able展開 (形式)</span><span class="sxs-lookup"><span data-stu-id="c2fac-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c2fac-105">構文</span><span class="sxs-lookup"><span data-stu-id="c2fac-105">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="c2fac-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="c2fac-106">Attributes and Elements</span></span>

<span data-ttu-id="c2fac-107">次のセクションでは、属性、子要素、`SelectionSetName` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2fac-107">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c2fac-108">属性</span><span class="sxs-lookup"><span data-stu-id="c2fac-108">Attributes</span></span>

<span data-ttu-id="c2fac-109">なし。</span><span class="sxs-lookup"><span data-stu-id="c2fac-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c2fac-110">子要素</span><span class="sxs-lookup"><span data-stu-id="c2fac-110">Child Elements</span></span>

<span data-ttu-id="c2fac-111">なし。</span><span class="sxs-lookup"><span data-stu-id="c2fac-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c2fac-112">親要素</span><span class="sxs-lookup"><span data-stu-id="c2fac-112">Parent Elements</span></span>

|<span data-ttu-id="c2fac-113">要素</span><span class="sxs-lookup"><span data-stu-id="c2fac-113">Element</span></span>|<span data-ttu-id="c2fac-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="c2fac-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c2fac-115">列挙 Able展開 (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="c2fac-115">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="c2fac-116">この定義によって展開される .NET コレクションオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="c2fac-116">Defines the .NET collection objects that are expanded by this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c2fac-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="c2fac-117">Text Value</span></span>

<span data-ttu-id="c2fac-118">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c2fac-118">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="c2fac-119">コメント</span><span class="sxs-lookup"><span data-stu-id="c2fac-119">Remarks</span></span>

<span data-ttu-id="c2fac-120">各定義には、1つ以上の型名、選択セット、または選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2fac-120">Each definition must specify one or more type names, a selection set, or a selection condition.</span></span>

<span data-ttu-id="c2fac-121">選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="c2fac-121">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="c2fac-122">たとえば、同じオブジェクトのセットに対してテーブルビューとリストビューを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="c2fac-122">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="c2fac-123">選択セットの定義の詳細については、「[ビューのオブジェクトセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2fac-123">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c2fac-124">参照</span><span class="sxs-lookup"><span data-stu-id="c2fac-124">See Also</span></span>

[<span data-ttu-id="c2fac-125">選択セットの定義</span><span class="sxs-lookup"><span data-stu-id="c2fac-125">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="c2fac-126">列挙 Able展開 (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="c2fac-126">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)

[<span data-ttu-id="c2fac-127">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="c2fac-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)