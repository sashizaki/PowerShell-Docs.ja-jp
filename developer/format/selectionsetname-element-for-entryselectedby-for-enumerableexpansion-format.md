---
title: EnumerableExpansion (形式) の EntrySelectedBy SelectionSetName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 936d09f2-2c48-49e8-ab2d-0c8729199a2e
caps.latest.revision: 8
ms.openlocfilehash: 8ba8931ea5e34f610878351396cad42023393ad6
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076261"
---
# <a name="selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="f777f-102">EnumerableExpansion の EntrySelectedBy の SelectionSetName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f777f-102">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="f777f-103">この定義で展開される .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="f777f-103">Specifies the set of .NET types that are expanded by this definition.</span></span>

<span data-ttu-id="f777f-104">構成要素 (形式) DefaultSettings 要素 (形式) EnumerableExpansions 要素 (形式) EnumerableExpansion 要素 (形式) EntrySelectedBy 要素の EntrySelectedBy の EnumerableExpansion (形式) SelectionSetName 要素EnumerableExpansion (形式)</span><span class="sxs-lookup"><span data-stu-id="f777f-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f777f-105">構文</span><span class="sxs-lookup"><span data-stu-id="f777f-105">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="f777f-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f777f-106">Attributes and Elements</span></span>

<span data-ttu-id="f777f-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionSetName`要素。</span><span class="sxs-lookup"><span data-stu-id="f777f-107">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f777f-108">属性</span><span class="sxs-lookup"><span data-stu-id="f777f-108">Attributes</span></span>

<span data-ttu-id="f777f-109">なし。</span><span class="sxs-lookup"><span data-stu-id="f777f-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f777f-110">子要素</span><span class="sxs-lookup"><span data-stu-id="f777f-110">Child Elements</span></span>

<span data-ttu-id="f777f-111">なし。</span><span class="sxs-lookup"><span data-stu-id="f777f-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f777f-112">親要素</span><span class="sxs-lookup"><span data-stu-id="f777f-112">Parent Elements</span></span>

|<span data-ttu-id="f777f-113">要素</span><span class="sxs-lookup"><span data-stu-id="f777f-113">Element</span></span>|<span data-ttu-id="f777f-114">説明</span><span class="sxs-lookup"><span data-stu-id="f777f-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f777f-115">EnumerableExpansion (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="f777f-115">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="f777f-116">この定義で展開される .NET コレクション オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="f777f-116">Defines the .NET collection objects that are expanded by this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f777f-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="f777f-117">Text Value</span></span>

<span data-ttu-id="f777f-118">選択範囲のセットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f777f-118">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="f777f-119">コメント</span><span class="sxs-lookup"><span data-stu-id="f777f-119">Remarks</span></span>

<span data-ttu-id="f777f-120">各定義には、1 つまたは複数の型名、選択範囲のセット、または選択条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f777f-120">Each definition must specify one or more type names, a selection set, or a selection condition.</span></span>

<span data-ttu-id="f777f-121">複数のビューで使用されるオブジェクトのグループを定義するときに、選択範囲のセットが通常使用されます。</span><span class="sxs-lookup"><span data-stu-id="f777f-121">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="f777f-122">たとえば、テーブル ビューと同じオブジェクトのセットのリスト ビューを作成する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f777f-122">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="f777f-123">選択範囲のセットを定義する詳細については、次を参照してください。[を定義する設定のビューのオブジェクトを](./defining-selection-sets.md)します。</span><span class="sxs-lookup"><span data-stu-id="f777f-123">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f777f-124">参照</span><span class="sxs-lookup"><span data-stu-id="f777f-124">See Also</span></span>

[<span data-ttu-id="f777f-125">選択範囲のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="f777f-125">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="f777f-126">EnumerableExpansion (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="f777f-126">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)

[<span data-ttu-id="f777f-127">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="f777f-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
