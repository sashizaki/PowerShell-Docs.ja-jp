---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSet の Name 要素 (書式)
description: SelectionSet の Name 要素 (書式)
ms.openlocfilehash: 98c13be6ea352055231fbdb3a60f0eb508f661b8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666462"
---
# <a name="name-element-for-selectionset-format"></a><span data-ttu-id="56993-103">SelectionSet の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="56993-103">Name Element for SelectionSet (Format)</span></span>

<span data-ttu-id="56993-104">選択セットを参照するために使用する名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="56993-104">Specifies the name used to reference the selection set.</span></span>

<span data-ttu-id="56993-105">Configuration 要素 (Format) SelectionSets 要素 (形式) Selectionsets 要素 (書式) Selectionsets (形式) の名前要素</span><span class="sxs-lookup"><span data-stu-id="56993-105">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Name Element of SelectionSet (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="56993-106">構文</span><span class="sxs-lookup"><span data-stu-id="56993-106">Syntax</span></span>

```xml
<Name>Name of selection set</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="56993-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="56993-107">Attributes and Elements</span></span>

<span data-ttu-id="56993-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `Name` ます。</span><span class="sxs-lookup"><span data-stu-id="56993-108">The following sections describe the attributes, child elements, and parent element of the `Name` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="56993-109">属性</span><span class="sxs-lookup"><span data-stu-id="56993-109">Attributes</span></span>

<span data-ttu-id="56993-110">なし。</span><span class="sxs-lookup"><span data-stu-id="56993-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="56993-111">子要素</span><span class="sxs-lookup"><span data-stu-id="56993-111">Child Elements</span></span>

<span data-ttu-id="56993-112">なし。</span><span class="sxs-lookup"><span data-stu-id="56993-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="56993-113">親要素</span><span class="sxs-lookup"><span data-stu-id="56993-113">Parent Elements</span></span>

|<span data-ttu-id="56993-114">要素</span><span class="sxs-lookup"><span data-stu-id="56993-114">Element</span></span>|<span data-ttu-id="56993-115">説明</span><span class="sxs-lookup"><span data-stu-id="56993-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="56993-116">SelectionSet 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="56993-116">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="56993-117">セットの名前で参照できる .NET オブジェクトの1つのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="56993-117">Defines a single set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="56993-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="56993-118">Text Value</span></span>

<span data-ttu-id="56993-119">選択セットを参照する名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="56993-119">Specify the name to reference the selection set.</span></span> <span data-ttu-id="56993-120">使用できる文字に関する制限はありません。</span><span class="sxs-lookup"><span data-stu-id="56993-120">There are no restrictions as to what characters can be used.</span></span>

## <a name="remarks"></a><span data-ttu-id="56993-121">解説</span><span class="sxs-lookup"><span data-stu-id="56993-121">Remarks</span></span>

<span data-ttu-id="56993-122">ここで指定された名前は、要素で使用され `SelectionSetName` ます。</span><span class="sxs-lookup"><span data-stu-id="56993-122">The name specified here is used in the `SelectionSetName` element.</span></span> <span data-ttu-id="56993-123">ビューで使用できる選択セット (ビューには複数の定義を含めることができます)、または選択条件を指定する場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="56993-123">The selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span> <span data-ttu-id="56993-124">選択セットの詳細については、「 [オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56993-124">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="56993-125">例</span><span class="sxs-lookup"><span data-stu-id="56993-125">Example</span></span>

<span data-ttu-id="56993-126">この例は、 `SelectionSet` 4 つの .net 型を定義する要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="56993-126">This example shows a `SelectionSet` element that defines four .NET types.</span></span> <span data-ttu-id="56993-127">選択セットの名前は "FileSystemTypes" です。</span><span class="sxs-lookup"><span data-stu-id="56993-127">The name of the selection set is "FileSystemTypes".</span></span>

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

## <a name="see-also"></a><span data-ttu-id="56993-128">参照</span><span class="sxs-lookup"><span data-stu-id="56993-128">See Also</span></span>

[<span data-ttu-id="56993-129">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="56993-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="56993-130">SelectionSet 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="56993-130">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="56993-131">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="56993-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
