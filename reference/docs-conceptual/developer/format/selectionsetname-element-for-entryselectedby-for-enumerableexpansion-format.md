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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368331"
---
# <a name="selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="e8b28-102">EnumerableExpansion の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e8b28-102">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="e8b28-103">この定義によって展開される .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="e8b28-103">Specifies the set of .NET types that are expanded by this definition.</span></span>

<span data-ttu-id="e8b28-104">Configuration 要素 (Format) DefaultSettings 要素 (format) には、EntrySelectedBy 要素 (format) の entryselectedby 要素 (format) を指定します。この場合、EntrySelectedBy の SelectionSetName 要素を指定します。列挙 Able展開 (形式)</span><span class="sxs-lookup"><span data-stu-id="e8b28-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e8b28-105">構文</span><span class="sxs-lookup"><span data-stu-id="e8b28-105">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="e8b28-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="e8b28-106">Attributes and Elements</span></span>

<span data-ttu-id="e8b28-107">次のセクションでは、`SelectionSetName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e8b28-107">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e8b28-108">属性</span><span class="sxs-lookup"><span data-stu-id="e8b28-108">Attributes</span></span>

<span data-ttu-id="e8b28-109">なし。</span><span class="sxs-lookup"><span data-stu-id="e8b28-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e8b28-110">子要素</span><span class="sxs-lookup"><span data-stu-id="e8b28-110">Child Elements</span></span>

<span data-ttu-id="e8b28-111">なし。</span><span class="sxs-lookup"><span data-stu-id="e8b28-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e8b28-112">親要素</span><span class="sxs-lookup"><span data-stu-id="e8b28-112">Parent Elements</span></span>

|<span data-ttu-id="e8b28-113">要素</span><span class="sxs-lookup"><span data-stu-id="e8b28-113">Element</span></span>|<span data-ttu-id="e8b28-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="e8b28-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e8b28-115">列挙 Able展開 (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="e8b28-115">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="e8b28-116">この定義によって展開される .NET コレクションオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="e8b28-116">Defines the .NET collection objects that are expanded by this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e8b28-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="e8b28-117">Text Value</span></span>

<span data-ttu-id="e8b28-118">選択セットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e8b28-118">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="e8b28-119">コメント</span><span class="sxs-lookup"><span data-stu-id="e8b28-119">Remarks</span></span>

<span data-ttu-id="e8b28-120">各定義には、1つ以上の型名、選択セット、または選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8b28-120">Each definition must specify one or more type names, a selection set, or a selection condition.</span></span>

<span data-ttu-id="e8b28-121">選択セットは、通常、複数のビューで使用されるオブジェクトのグループを定義する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="e8b28-121">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="e8b28-122">たとえば、同じオブジェクトのセットに対してテーブルビューとリストビューを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e8b28-122">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="e8b28-123">選択セットの定義の詳細については、「[ビューのオブジェクトセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8b28-123">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e8b28-124">参照</span><span class="sxs-lookup"><span data-stu-id="e8b28-124">See Also</span></span>

[<span data-ttu-id="e8b28-125">選択セットの定義</span><span class="sxs-lookup"><span data-stu-id="e8b28-125">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="e8b28-126">列挙 Able展開 (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="e8b28-126">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)

[<span data-ttu-id="e8b28-127">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="e8b28-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
