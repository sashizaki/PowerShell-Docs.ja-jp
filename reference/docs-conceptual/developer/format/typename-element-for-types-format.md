---
title: 型の TypeName 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 40fad73c66124d6c3b0d969b4268713a492c963a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772537"
---
# <a name="typename-element-for-types-format"></a><span data-ttu-id="f5df2-102">Types の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f5df2-102">TypeName Element for Types (Format)</span></span>

<span data-ttu-id="f5df2-103">選択セットに属するオブジェクトの .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5df2-103">Specifies the .NET type of an object that belongs to the selection set.</span></span>

<span data-ttu-id="f5df2-104">Configuration 要素 (Format) SelectionSets 要素 (形式) Selectionsets 要素 (format) Types 要素 (format) 型の TypeName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="f5df2-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format) TypeName Element of Types (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f5df2-105">構文</span><span class="sxs-lookup"><span data-stu-id="f5df2-105">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f5df2-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f5df2-106">Attributes and Elements</span></span>

<span data-ttu-id="f5df2-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。</span><span class="sxs-lookup"><span data-stu-id="f5df2-107">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span> <span data-ttu-id="f5df2-108">`TypeName`選択セットには、少なくとも1つの要素を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5df2-108">At least one `TypeName` element must be included in the selection set.</span></span>

### <a name="attributes"></a><span data-ttu-id="f5df2-109">属性</span><span class="sxs-lookup"><span data-stu-id="f5df2-109">Attributes</span></span>

<span data-ttu-id="f5df2-110">なし。</span><span class="sxs-lookup"><span data-stu-id="f5df2-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f5df2-111">子要素</span><span class="sxs-lookup"><span data-stu-id="f5df2-111">Child Elements</span></span>

<span data-ttu-id="f5df2-112">なし。</span><span class="sxs-lookup"><span data-stu-id="f5df2-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f5df2-113">親要素</span><span class="sxs-lookup"><span data-stu-id="f5df2-113">Parent Elements</span></span>

|<span data-ttu-id="f5df2-114">要素</span><span class="sxs-lookup"><span data-stu-id="f5df2-114">Element</span></span>|<span data-ttu-id="f5df2-115">説明</span><span class="sxs-lookup"><span data-stu-id="f5df2-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f5df2-116">Types 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="f5df2-116">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="f5df2-117">選択セット内の .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="f5df2-117">Defines the .NET objects that are in the selection set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f5df2-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="f5df2-118">Text Value</span></span>

<span data-ttu-id="f5df2-119">.NET 型の完全修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5df2-119">Specify the fully qualified name for the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="f5df2-120">解説</span><span class="sxs-lookup"><span data-stu-id="f5df2-120">Remarks</span></span>

<span data-ttu-id="f5df2-121">継承によって関連付けられたオブジェクトのセットなど、1つの名前を使用して参照する関連オブジェクトのセットがある場合は、選択セットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5df2-121">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="f5df2-122">ビューを定義するときに、各ビュー内のすべてのオブジェクトを一覧表示するのではなく、選択したセットの名前を使用してオブジェクトのセットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f5df2-122">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="f5df2-123">共通選択セットは、書式設定ファイルのビューを定義するときに、名前によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="f5df2-123">Common selection sets are specified by their name when defining the views of the formatting file.</span></span> <span data-ttu-id="f5df2-124">このような場合は、 `SelectionSetName` ビューの要素の子要素によって `ViewSelectedBy` セットが指定されます。</span><span class="sxs-lookup"><span data-stu-id="f5df2-124">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` element for the view specifies the set.</span></span> <span data-ttu-id="f5df2-125">ただし、ビューのエントリごとに、そのビューのエントリのみに適用される選択セットを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f5df2-125">However, different entries of a view can also specify a selection set that applies to only that entry of the view.</span></span> <span data-ttu-id="f5df2-126">選択セットの詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5df2-126">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="f5df2-127">例</span><span class="sxs-lookup"><span data-stu-id="f5df2-127">Example</span></span>

<span data-ttu-id="f5df2-128">次の例は、 `SelectionSet` 4 つの .net 型を定義する要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="f5df2-128">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f5df2-129">参照</span><span class="sxs-lookup"><span data-stu-id="f5df2-129">See Also</span></span>

[<span data-ttu-id="f5df2-130">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="f5df2-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="f5df2-131">SelectionSet 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f5df2-131">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="f5df2-132">SelectionSets 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="f5df2-132">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="f5df2-133">Types 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="f5df2-133">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="f5df2-134">Windows PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="f5df2-134">Writing a Windows PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
