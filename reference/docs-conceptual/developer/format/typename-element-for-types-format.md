---
title: 型の TypeName 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0595b99e-b438-4240-b47b-555cf0316f33
caps.latest.revision: 15
ms.openlocfilehash: bd5baa03c2050b2c3bbe1d7697c253d923175d39
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368031"
---
# <a name="typename-element-for-types-format"></a><span data-ttu-id="74938-102">Types の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="74938-102">TypeName Element for Types (Format)</span></span>

<span data-ttu-id="74938-103">選択セットに属するオブジェクトの .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="74938-103">Specifies the .NET type of an object that belongs to the selection set.</span></span>

<span data-ttu-id="74938-104">Configuration 要素 (Format) SelectionSets 要素 (形式) Selectionsets 要素 (format) Types 要素 (format) 型の TypeName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="74938-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format) TypeName Element of Types (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="74938-105">構文</span><span class="sxs-lookup"><span data-stu-id="74938-105">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="74938-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="74938-106">Attributes and Elements</span></span>

<span data-ttu-id="74938-107">次のセクションでは、`TypeName` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="74938-107">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span> <span data-ttu-id="74938-108">選択セットには、少なくとも1つの `TypeName` 要素が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="74938-108">At least one `TypeName` element must be included in the selection set.</span></span>

### <a name="attributes"></a><span data-ttu-id="74938-109">属性</span><span class="sxs-lookup"><span data-stu-id="74938-109">Attributes</span></span>

<span data-ttu-id="74938-110">なし。</span><span class="sxs-lookup"><span data-stu-id="74938-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="74938-111">子要素</span><span class="sxs-lookup"><span data-stu-id="74938-111">Child Elements</span></span>

<span data-ttu-id="74938-112">なし。</span><span class="sxs-lookup"><span data-stu-id="74938-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="74938-113">親要素</span><span class="sxs-lookup"><span data-stu-id="74938-113">Parent Elements</span></span>

|<span data-ttu-id="74938-114">要素</span><span class="sxs-lookup"><span data-stu-id="74938-114">Element</span></span>|<span data-ttu-id="74938-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="74938-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="74938-116">Types 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="74938-116">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="74938-117">選択セット内の .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="74938-117">Defines the .NET objects that are in the selection set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="74938-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="74938-118">Text Value</span></span>

<span data-ttu-id="74938-119">.NET 型の完全修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="74938-119">Specify the fully qualified name for the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="74938-120">コメント</span><span class="sxs-lookup"><span data-stu-id="74938-120">Remarks</span></span>

<span data-ttu-id="74938-121">継承によって関連付けられたオブジェクトのセットなど、1つの名前を使用して参照する関連オブジェクトのセットがある場合は、選択セットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="74938-121">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="74938-122">ビューを定義するときに、各ビュー内のすべてのオブジェクトを一覧表示するのではなく、選択したセットの名前を使用してオブジェクトのセットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="74938-122">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="74938-123">共通選択セットは、書式設定ファイルのビューを定義するときに、名前によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="74938-123">Common selection sets are specified by their name when defining the views of the formatting file.</span></span> <span data-ttu-id="74938-124">このような場合、ビューの `ViewSelectedBy` 要素の @no__t 0 子要素は、セットを指定します。</span><span class="sxs-lookup"><span data-stu-id="74938-124">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` element for the view specifies the set.</span></span> <span data-ttu-id="74938-125">ただし、ビューのエントリごとに、そのビューのエントリのみに適用される選択セットを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="74938-125">However, different entries of a view can also specify a selection set that applies to only that entry of the view.</span></span> <span data-ttu-id="74938-126">選択セットの詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74938-126">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="74938-127">例</span><span class="sxs-lookup"><span data-stu-id="74938-127">Example</span></span>

<span data-ttu-id="74938-128">次の例は、4つの .NET 型を定義する @no__t 0 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="74938-128">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

```
<SelectionSets>
  <SelectionSet>
    <Name>FileSystemTypes</Name>
    <Types>
     <TypeName>System.IO.DirectoryInfo</TypeName>
     <TypeName>System.IO.FileInfo</TypeName>
     <TypeName>Deserialized.System.IO.DirectoryInfo</TypeName>
     <TypeName>Deserialized.System.IO.FileInfo</TypeName>
    </Types>
  </SelectionSet>
</SelectionSets>
```

## <a name="see-also"></a><span data-ttu-id="74938-129">参照</span><span class="sxs-lookup"><span data-stu-id="74938-129">See Also</span></span>

[<span data-ttu-id="74938-130">選択セットの定義</span><span class="sxs-lookup"><span data-stu-id="74938-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="74938-131">SelectionSet 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="74938-131">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="74938-132">SelectionSets 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="74938-132">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="74938-133">Types 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="74938-133">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="74938-134">Windows PowerShell のフォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="74938-134">Writing a Windows PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
