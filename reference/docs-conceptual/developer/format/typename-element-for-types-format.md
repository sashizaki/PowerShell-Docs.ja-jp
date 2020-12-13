---
ms.date: 09/13/2016
ms.topic: reference
title: Types の TypeName 要素 (書式)
description: Types の TypeName 要素 (書式)
ms.openlocfilehash: c656b8e7e5877b72ff2164e5b417857273cada61
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664609"
---
# <a name="typename-element-for-types-format"></a><span data-ttu-id="f6374-103">Types の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f6374-103">TypeName Element for Types (Format)</span></span>

<span data-ttu-id="f6374-104">選択セットに属するオブジェクトの .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="f6374-104">Specifies the .NET type of an object that belongs to the selection set.</span></span>

<span data-ttu-id="f6374-105">Configuration 要素 (Format) SelectionSets 要素 (形式) Selectionsets 要素 (format) Types 要素 (format) 型の TypeName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="f6374-105">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format) TypeName Element of Types (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f6374-106">構文</span><span class="sxs-lookup"><span data-stu-id="f6374-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f6374-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f6374-107">Attributes and Elements</span></span>

<span data-ttu-id="f6374-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。</span><span class="sxs-lookup"><span data-stu-id="f6374-108">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span> <span data-ttu-id="f6374-109">`TypeName`選択セットには、少なくとも1つの要素を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6374-109">At least one `TypeName` element must be included in the selection set.</span></span>

### <a name="attributes"></a><span data-ttu-id="f6374-110">属性</span><span class="sxs-lookup"><span data-stu-id="f6374-110">Attributes</span></span>

<span data-ttu-id="f6374-111">なし。</span><span class="sxs-lookup"><span data-stu-id="f6374-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f6374-112">子要素</span><span class="sxs-lookup"><span data-stu-id="f6374-112">Child Elements</span></span>

<span data-ttu-id="f6374-113">なし。</span><span class="sxs-lookup"><span data-stu-id="f6374-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f6374-114">親要素</span><span class="sxs-lookup"><span data-stu-id="f6374-114">Parent Elements</span></span>

|<span data-ttu-id="f6374-115">要素</span><span class="sxs-lookup"><span data-stu-id="f6374-115">Element</span></span>|<span data-ttu-id="f6374-116">説明</span><span class="sxs-lookup"><span data-stu-id="f6374-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f6374-117">Types 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="f6374-117">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="f6374-118">選択セット内の .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="f6374-118">Defines the .NET objects that are in the selection set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f6374-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="f6374-119">Text Value</span></span>

<span data-ttu-id="f6374-120">.NET 型の完全修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="f6374-120">Specify the fully qualified name for the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="f6374-121">解説</span><span class="sxs-lookup"><span data-stu-id="f6374-121">Remarks</span></span>

<span data-ttu-id="f6374-122">継承によって関連付けられたオブジェクトのセットなど、1つの名前を使用して参照する関連オブジェクトのセットがある場合は、選択セットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f6374-122">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="f6374-123">ビューを定義するときに、各ビュー内のすべてのオブジェクトを一覧表示するのではなく、選択したセットの名前を使用してオブジェクトのセットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f6374-123">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="f6374-124">共通選択セットは、書式設定ファイルのビューを定義するときに、名前によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="f6374-124">Common selection sets are specified by their name when defining the views of the formatting file.</span></span> <span data-ttu-id="f6374-125">このような場合は、 `SelectionSetName` ビューの要素の子要素によって `ViewSelectedBy` セットが指定されます。</span><span class="sxs-lookup"><span data-stu-id="f6374-125">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` element for the view specifies the set.</span></span> <span data-ttu-id="f6374-126">ただし、ビューのエントリごとに、そのビューのエントリのみに適用される選択セットを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f6374-126">However, different entries of a view can also specify a selection set that applies to only that entry of the view.</span></span> <span data-ttu-id="f6374-127">選択セットの詳細については、「 [オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6374-127">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="f6374-128">例</span><span class="sxs-lookup"><span data-stu-id="f6374-128">Example</span></span>

<span data-ttu-id="f6374-129">次の例は、 `SelectionSet` 4 つの .net 型を定義する要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="f6374-129">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f6374-130">参照</span><span class="sxs-lookup"><span data-stu-id="f6374-130">See Also</span></span>

[<span data-ttu-id="f6374-131">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="f6374-131">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="f6374-132">SelectionSet 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f6374-132">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="f6374-133">SelectionSets 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f6374-133">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="f6374-134">Types 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="f6374-134">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="f6374-135">Windows PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="f6374-135">Writing a Windows PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
