---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSets 要素 (書式)
description: SelectionSets 要素 (書式)
ms.openlocfilehash: e5c928dfb82bc6963b4a87aef9ec06d34cacfdcb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654921"
---
# <a name="selectionsets-element-format"></a><span data-ttu-id="174e2-103">SelectionSets 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="174e2-103">SelectionSets Element (Format)</span></span>

<span data-ttu-id="174e2-104">書式設定ファイルのすべてのビューで使用できる .NET オブジェクトの共通セットを定義します。</span><span class="sxs-lookup"><span data-stu-id="174e2-104">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span> <span data-ttu-id="174e2-105">書式設定ファイルのビューおよびコントロールは、選択セットの名前のみを使用して、オブジェクトの完全なセットを参照できます。</span><span class="sxs-lookup"><span data-stu-id="174e2-105">The views and controls of the formatting file can reference the complete set of objects by using only the name of the selection set.</span></span>

<span data-ttu-id="174e2-106">構成要素 SelectionSets 要素の形式</span><span class="sxs-lookup"><span data-stu-id="174e2-106">Configuration Element SelectionSets Element Format</span></span>

## <a name="syntax"></a><span data-ttu-id="174e2-107">構文</span><span class="sxs-lookup"><span data-stu-id="174e2-107">Syntax</span></span>

```xml
<SelectionSets>
  <SelectionSet>...</SelectionSet>
</SelectionSets>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="174e2-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="174e2-108">Attributes and Elements</span></span>

<span data-ttu-id="174e2-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `SelectionSets` ます。</span><span class="sxs-lookup"><span data-stu-id="174e2-109">The following sections describe the attributes, child elements, and parent element of the `SelectionSets` element.</span></span> <span data-ttu-id="174e2-110">各子要素は、セットの名前で参照できるオブジェクトのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="174e2-110">Each child element defines a set of objects that can be referenced by the name of the set.</span></span> <span data-ttu-id="174e2-111">子要素の順序は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="174e2-111">The order of the child elements is not significant.</span></span>

### <a name="attributes"></a><span data-ttu-id="174e2-112">属性</span><span class="sxs-lookup"><span data-stu-id="174e2-112">Attributes</span></span>

<span data-ttu-id="174e2-113">なし。</span><span class="sxs-lookup"><span data-stu-id="174e2-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="174e2-114">子要素</span><span class="sxs-lookup"><span data-stu-id="174e2-114">Child Elements</span></span>

|<span data-ttu-id="174e2-115">要素</span><span class="sxs-lookup"><span data-stu-id="174e2-115">Element</span></span>|<span data-ttu-id="174e2-116">説明</span><span class="sxs-lookup"><span data-stu-id="174e2-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="174e2-117">SelectionSet 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="174e2-117">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="174e2-118">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="174e2-118">Required element.</span></span><br /><br /> <span data-ttu-id="174e2-119">セットの名前で参照できる .NET オブジェクトの1つのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="174e2-119">Defines a single set of .NET objects that can be referenced by the name of the set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="174e2-120">親要素</span><span class="sxs-lookup"><span data-stu-id="174e2-120">Parent Elements</span></span>

|<span data-ttu-id="174e2-121">要素</span><span class="sxs-lookup"><span data-stu-id="174e2-121">Element</span></span>|<span data-ttu-id="174e2-122">説明</span><span class="sxs-lookup"><span data-stu-id="174e2-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="174e2-123">Configuration 要素</span><span class="sxs-lookup"><span data-stu-id="174e2-123">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="174e2-124">書式設定ファイルのトップレベルの要素を表します。</span><span class="sxs-lookup"><span data-stu-id="174e2-124">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="174e2-125">解説</span><span class="sxs-lookup"><span data-stu-id="174e2-125">Remarks</span></span>

<span data-ttu-id="174e2-126">継承によって関連付けられたオブジェクトのセットなど、1つの名前を使用して参照する関連オブジェクトのセットがある場合は、選択セットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="174e2-126">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="174e2-127">ビューを定義するときに、各ビュー内のすべてのオブジェクトを一覧表示するのではなく、選択したセットの名前を使用してオブジェクトのセットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="174e2-127">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="174e2-128">共通選択セットは、書式設定ファイルのビューまたはビューの定義を定義するときに、名前によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="174e2-128">Common selection sets are specified by their name when defining the views of the formatting file or the definitions of the views.</span></span> <span data-ttu-id="174e2-129">このような場合、 `SelectionSetName` 要素と要素の子要素は、 `ViewSelectedBy` `EntrySelectedBy` 使用するセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="174e2-129">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` and `EntrySelectedBy` elements specifies the set to be used.</span></span> <span data-ttu-id="174e2-130">選択セットの詳細については、「 [オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="174e2-130">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="174e2-131">参照</span><span class="sxs-lookup"><span data-stu-id="174e2-131">See Also</span></span>

[<span data-ttu-id="174e2-132">Configuration 要素</span><span class="sxs-lookup"><span data-stu-id="174e2-132">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="174e2-133">選択セットを定義する</span><span class="sxs-lookup"><span data-stu-id="174e2-133">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="174e2-134">SelectionSet 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="174e2-134">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="174e2-135">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="174e2-135">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
