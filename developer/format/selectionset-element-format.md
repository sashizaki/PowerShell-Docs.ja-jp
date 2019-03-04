---
title: SelectionSet 要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 848e7acd-d578-4fd1-a575-c0c3b9b5e68a
caps.latest.revision: 17
ms.openlocfilehash: c809aa6c3a40d16cfd2fd99065a846d265ec0f61
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861158"
---
# <a name="selectionset-element-format"></a><span data-ttu-id="6e855-102">SelectionSet 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="6e855-102">SelectionSet Element (Format)</span></span>

<span data-ttu-id="6e855-103">セットの名前で参照できる .NET オブジェクトのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="6e855-103">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>

<span data-ttu-id="6e855-104">構成要素 (形式) SelectionSets 要素 (形式) SelectionSet 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="6e855-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6e855-105">構文</span><span class="sxs-lookup"><span data-stu-id="6e855-105">Syntax</span></span>

```xml
<SelectionSet>
  <Name>SelectionSetName</Name>
  <Types>...</Types>
</SelectionSet>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6e855-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="6e855-106">Attributes and Elements</span></span>

<span data-ttu-id="6e855-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionSet`要素。</span><span class="sxs-lookup"><span data-stu-id="6e855-107">The following sections describe the attributes, child elements, and the parent element of the `SelectionSet` element.</span></span> <span data-ttu-id="6e855-108">各選択セットには、名前が必要ですし、一連の .NET オブジェクトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e855-108">Each selection set must have a name, and it must specify the .NET objects of the set.</span></span>

### <a name="attributes"></a><span data-ttu-id="6e855-109">属性</span><span class="sxs-lookup"><span data-stu-id="6e855-109">Attributes</span></span>

<span data-ttu-id="6e855-110">なし。</span><span class="sxs-lookup"><span data-stu-id="6e855-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6e855-111">子要素</span><span class="sxs-lookup"><span data-stu-id="6e855-111">Child Elements</span></span>

|<span data-ttu-id="6e855-112">要素</span><span class="sxs-lookup"><span data-stu-id="6e855-112">Element</span></span>|<span data-ttu-id="6e855-113">説明</span><span class="sxs-lookup"><span data-stu-id="6e855-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6e855-114">SelectionSet (形式) の name 要素</span><span class="sxs-lookup"><span data-stu-id="6e855-114">Name Element for SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)|<span data-ttu-id="6e855-115">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="6e855-115">Required element.</span></span><br /><br /> <span data-ttu-id="6e855-116">選択範囲のセットを参照するための名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e855-116">Specifies the name used to reference the selection set.</span></span>|
|[<span data-ttu-id="6e855-117">型の要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="6e855-117">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="6e855-118">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="6e855-118">Required element.</span></span><br /><br /> <span data-ttu-id="6e855-119">選択範囲で設定された .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="6e855-119">Defines the .NET objects that are in the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6e855-120">親要素</span><span class="sxs-lookup"><span data-stu-id="6e855-120">Parent Elements</span></span>

|<span data-ttu-id="6e855-121">要素</span><span class="sxs-lookup"><span data-stu-id="6e855-121">Element</span></span>|<span data-ttu-id="6e855-122">説明</span><span class="sxs-lookup"><span data-stu-id="6e855-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6e855-123">SelectionSets 要素の形式</span><span class="sxs-lookup"><span data-stu-id="6e855-123">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="6e855-124">書式設定ファイルのすべてのビューで使用できる .NET オブジェクトの共通セットを定義します。</span><span class="sxs-lookup"><span data-stu-id="6e855-124">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6e855-125">コメント</span><span class="sxs-lookup"><span data-stu-id="6e855-125">Remarks</span></span>

<span data-ttu-id="6e855-126">継承によって関連付けられているオブジェクトのセットなどの 1 つの名前を使用して参照する関連のオブジェクトのセットがある場合は、選択範囲のセットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e855-126">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="6e855-127">ビューを定義するときに、それぞれのビュー内のすべてのオブジェクトを一覧表示するのではなく設定の選択範囲の名前を使用してオブジェクトのセットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6e855-127">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="6e855-128">一般的な選択範囲のセットは、書式設定ファイルのビューまたはビューの定義を定義するときに、名前によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="6e855-128">Common selection sets are specified by their name when defining the views of the formatting file or the definitions of the views.</span></span> <span data-ttu-id="6e855-129">このような場合、`SelectionSetName`の子要素、`ViewSelectedBy`と`EntrySelectedBy`要素を使用するデータセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="6e855-129">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` and `EntrySelectedBy` elements specifies the set to be used.</span></span> <span data-ttu-id="6e855-130">選択範囲のセットの詳細については、次を参照してください。[オブジェクト設定を定義する](./defining-selection-sets.md)します。</span><span class="sxs-lookup"><span data-stu-id="6e855-130">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="6e855-131">例</span><span class="sxs-lookup"><span data-stu-id="6e855-131">Example</span></span>

<span data-ttu-id="6e855-132">次の例は、 `SelectionSet` 4 つの .NET 型を定義する要素。</span><span class="sxs-lookup"><span data-stu-id="6e855-132">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="6e855-133">参照</span><span class="sxs-lookup"><span data-stu-id="6e855-133">See Also</span></span>

[<span data-ttu-id="6e855-134">選択範囲のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="6e855-134">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="6e855-135">SelectionSet (形式) の name 要素</span><span class="sxs-lookup"><span data-stu-id="6e855-135">Name Element of SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)

[<span data-ttu-id="6e855-136">SelectionSets 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="6e855-136">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="6e855-137">型の要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="6e855-137">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="6e855-138">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="6e855-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
