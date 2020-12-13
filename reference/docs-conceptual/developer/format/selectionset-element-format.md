---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSet 要素 (書式)
description: SelectionSet 要素 (書式)
ms.openlocfilehash: 944aa83569ad8ca789746a71f60e5da5c19fbf01
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647877"
---
# <a name="selectionset-element-format"></a><span data-ttu-id="52174-103">SelectionSet 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="52174-103">SelectionSet Element (Format)</span></span>

<span data-ttu-id="52174-104">セットの名前で参照できる .NET オブジェクトのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="52174-104">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>

<span data-ttu-id="52174-105">Configuration 要素 (Format) SelectionSets 要素 (書式) Selectionsets 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="52174-105">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="52174-106">構文</span><span class="sxs-lookup"><span data-stu-id="52174-106">Syntax</span></span>

```xml
<SelectionSet>
  <Name>SelectionSetName</Name>
  <Types>...</Types>
</SelectionSet>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="52174-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="52174-107">Attributes and Elements</span></span>

<span data-ttu-id="52174-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSet` ます。</span><span class="sxs-lookup"><span data-stu-id="52174-108">The following sections describe the attributes, child elements, and the parent element of the `SelectionSet` element.</span></span> <span data-ttu-id="52174-109">各選択セットには名前が必要であり、セットの .NET オブジェクトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52174-109">Each selection set must have a name, and it must specify the .NET objects of the set.</span></span>

### <a name="attributes"></a><span data-ttu-id="52174-110">属性</span><span class="sxs-lookup"><span data-stu-id="52174-110">Attributes</span></span>

<span data-ttu-id="52174-111">なし。</span><span class="sxs-lookup"><span data-stu-id="52174-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="52174-112">子要素</span><span class="sxs-lookup"><span data-stu-id="52174-112">Child Elements</span></span>

|<span data-ttu-id="52174-113">要素</span><span class="sxs-lookup"><span data-stu-id="52174-113">Element</span></span>|<span data-ttu-id="52174-114">説明</span><span class="sxs-lookup"><span data-stu-id="52174-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="52174-115">SelectionSet の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="52174-115">Name Element for SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)|<span data-ttu-id="52174-116">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="52174-116">Required element.</span></span><br /><br /> <span data-ttu-id="52174-117">選択セットを参照するために使用する名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="52174-117">Specifies the name used to reference the selection set.</span></span>|
|[<span data-ttu-id="52174-118">Types 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="52174-118">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="52174-119">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="52174-119">Required element.</span></span><br /><br /> <span data-ttu-id="52174-120">選択セット内の .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="52174-120">Defines the .NET objects that are in the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="52174-121">親要素</span><span class="sxs-lookup"><span data-stu-id="52174-121">Parent Elements</span></span>

|<span data-ttu-id="52174-122">要素</span><span class="sxs-lookup"><span data-stu-id="52174-122">Element</span></span>|<span data-ttu-id="52174-123">説明</span><span class="sxs-lookup"><span data-stu-id="52174-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="52174-124">SelectionSets 要素の形式</span><span class="sxs-lookup"><span data-stu-id="52174-124">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="52174-125">書式設定ファイルのすべてのビューで使用できる .NET オブジェクトの共通セットを定義します。</span><span class="sxs-lookup"><span data-stu-id="52174-125">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="52174-126">解説</span><span class="sxs-lookup"><span data-stu-id="52174-126">Remarks</span></span>

<span data-ttu-id="52174-127">継承によって関連付けられたオブジェクトのセットなど、1つの名前を使用して参照する関連オブジェクトのセットがある場合は、選択セットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="52174-127">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="52174-128">ビューを定義するときに、各ビュー内のすべてのオブジェクトを一覧表示するのではなく、選択したセットの名前を使用してオブジェクトのセットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="52174-128">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="52174-129">共通選択セットは、書式設定ファイルのビューまたはビューの定義を定義するときに、名前によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="52174-129">Common selection sets are specified by their name when defining the views of the formatting file or the definitions of the views.</span></span> <span data-ttu-id="52174-130">このような場合、 `SelectionSetName` 要素と要素の子要素は、 `ViewSelectedBy` `EntrySelectedBy` 使用するセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="52174-130">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` and `EntrySelectedBy` elements specifies the set to be used.</span></span> <span data-ttu-id="52174-131">選択セットの詳細については、「 [オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52174-131">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="52174-132">例</span><span class="sxs-lookup"><span data-stu-id="52174-132">Example</span></span>

<span data-ttu-id="52174-133">次の例は、 `SelectionSet` 4 つの .net 型を定義する要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="52174-133">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="52174-134">参照</span><span class="sxs-lookup"><span data-stu-id="52174-134">See Also</span></span>

[<span data-ttu-id="52174-135">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="52174-135">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="52174-136">SelectionSet の Name 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="52174-136">Name Element of SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)

[<span data-ttu-id="52174-137">SelectionSets 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="52174-137">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="52174-138">Types 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="52174-138">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="52174-139">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="52174-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
