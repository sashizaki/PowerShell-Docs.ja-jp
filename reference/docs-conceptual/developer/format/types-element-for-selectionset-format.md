---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSet の Types 要素 (書式)
description: SelectionSet の Types 要素 (書式)
ms.openlocfilehash: ff3c24e7f52f862dc416b88d50983196ce907012
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645464"
---
# <a name="types-element-for-selectionset-format"></a><span data-ttu-id="a46bb-103">SelectionSet の Types 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a46bb-103">Types Element for SelectionSet (Format)</span></span>

<span data-ttu-id="a46bb-104">選択セット内の .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="a46bb-104">Defines the .NET objects that are in the selection set.</span></span>

<span data-ttu-id="a46bb-105">Configuration 要素 (Format) SelectionSets 要素 (書式) Selectionsets Element (format) Types 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a46bb-105">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a46bb-106">構文</span><span class="sxs-lookup"><span data-stu-id="a46bb-106">Syntax</span></span>

```xml
<Types>
  <TypeName>Nameof.NetType</TypeName>
</Types>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="a46bb-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a46bb-107">Attributes and Elements</span></span>

<span data-ttu-id="a46bb-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `Types` ます。</span><span class="sxs-lookup"><span data-stu-id="a46bb-108">The following sections describe the attributes, child elements, and the parent element of the `Types` element.</span></span> <span data-ttu-id="a46bb-109">少なくとも1つの子要素が必要ですが、追加できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="a46bb-109">There must be at least one child element, but there is no maximum limit to the number of child elements that can be added.</span></span>

### <a name="attributes"></a><span data-ttu-id="a46bb-110">属性</span><span class="sxs-lookup"><span data-stu-id="a46bb-110">Attributes</span></span>

<span data-ttu-id="a46bb-111">なし。</span><span class="sxs-lookup"><span data-stu-id="a46bb-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a46bb-112">子要素</span><span class="sxs-lookup"><span data-stu-id="a46bb-112">Child Elements</span></span>

|<span data-ttu-id="a46bb-113">要素</span><span class="sxs-lookup"><span data-stu-id="a46bb-113">Element</span></span>|<span data-ttu-id="a46bb-114">説明</span><span class="sxs-lookup"><span data-stu-id="a46bb-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a46bb-115">型の TypeName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="a46bb-115">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)|<span data-ttu-id="a46bb-116">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="a46bb-116">Required element.</span></span><br /><br /> <span data-ttu-id="a46bb-117">選択セットに属する .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="a46bb-117">Specifies the .NET object that belongs to the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a46bb-118">親要素</span><span class="sxs-lookup"><span data-stu-id="a46bb-118">Parent Elements</span></span>

|<span data-ttu-id="a46bb-119">要素</span><span class="sxs-lookup"><span data-stu-id="a46bb-119">Element</span></span>|<span data-ttu-id="a46bb-120">説明</span><span class="sxs-lookup"><span data-stu-id="a46bb-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a46bb-121">SelectionSet 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a46bb-121">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="a46bb-122">セットの名前で参照できる .NET オブジェクトのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="a46bb-122">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a46bb-123">解説</span><span class="sxs-lookup"><span data-stu-id="a46bb-123">Remarks</span></span>

<span data-ttu-id="a46bb-124">この要素によって定義されるオブジェクトは、ビューで使用できる選択セット、ビューの定義 (ビューは複数の定義を持つことができます)、または選択条件を指定するときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="a46bb-124">The objects defined by this element make up a selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span>  <span data-ttu-id="a46bb-125">選択セットの詳細については、「 [オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a46bb-125">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="a46bb-126">例</span><span class="sxs-lookup"><span data-stu-id="a46bb-126">Example</span></span>

<span data-ttu-id="a46bb-127">この例は、 `SelectionSet` 4 つの .net 型を定義する要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="a46bb-127">This example shows a `SelectionSet` element that defines four .NET types.</span></span>

```xml
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

## <a name="see-also"></a><span data-ttu-id="a46bb-128">参照</span><span class="sxs-lookup"><span data-stu-id="a46bb-128">See Also</span></span>

[<span data-ttu-id="a46bb-129">オブジェクトのセットの定義</span><span class="sxs-lookup"><span data-stu-id="a46bb-129">Defining Sets of Objects</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="a46bb-130">SelectionSet 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a46bb-130">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="a46bb-131">型の TypeName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="a46bb-131">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)

[<span data-ttu-id="a46bb-132">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="a46bb-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
