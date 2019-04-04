---
title: TypeName 要素の種類 (形式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0595b99e-b438-4240-b47b-555cf0316f33
caps.latest.revision: 15
ms.openlocfilehash: bd5baa03c2050b2c3bbe1d7697c253d923175d39
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057928"
---
# <a name="typename-element-for-types-format"></a><span data-ttu-id="ec9e7-102">Types の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="ec9e7-102">TypeName Element for Types (Format)</span></span>

<span data-ttu-id="ec9e7-103">選択範囲のセットに属しているオブジェクトの .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="ec9e7-103">Specifies the .NET type of an object that belongs to the selection set.</span></span>

<span data-ttu-id="ec9e7-104">構成要素 (形式) SelectionSets 要素 (形式) SelectionSet 要素 (形式) の種類 (形式) の要素 (形式) の TypeName 要素の型します。</span><span class="sxs-lookup"><span data-stu-id="ec9e7-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format) TypeName Element of Types (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ec9e7-105">構文</span><span class="sxs-lookup"><span data-stu-id="ec9e7-105">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ec9e7-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="ec9e7-106">Attributes and Elements</span></span>

<span data-ttu-id="ec9e7-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`TypeName`要素。</span><span class="sxs-lookup"><span data-stu-id="ec9e7-107">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span> <span data-ttu-id="ec9e7-108">少なくとも 1 つ`TypeName`選択セットに要素を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec9e7-108">At least one `TypeName` element must be included in the selection set.</span></span>

### <a name="attributes"></a><span data-ttu-id="ec9e7-109">属性</span><span class="sxs-lookup"><span data-stu-id="ec9e7-109">Attributes</span></span>

<span data-ttu-id="ec9e7-110">なし。</span><span class="sxs-lookup"><span data-stu-id="ec9e7-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ec9e7-111">子要素</span><span class="sxs-lookup"><span data-stu-id="ec9e7-111">Child Elements</span></span>

<span data-ttu-id="ec9e7-112">なし。</span><span class="sxs-lookup"><span data-stu-id="ec9e7-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ec9e7-113">親要素</span><span class="sxs-lookup"><span data-stu-id="ec9e7-113">Parent Elements</span></span>

|<span data-ttu-id="ec9e7-114">要素</span><span class="sxs-lookup"><span data-stu-id="ec9e7-114">Element</span></span>|<span data-ttu-id="ec9e7-115">説明</span><span class="sxs-lookup"><span data-stu-id="ec9e7-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ec9e7-116">型の要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ec9e7-116">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="ec9e7-117">選択範囲で設定された .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="ec9e7-117">Defines the .NET objects that are in the selection set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ec9e7-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="ec9e7-118">Text Value</span></span>

<span data-ttu-id="ec9e7-119">.NET 型の完全修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ec9e7-119">Specify the fully qualified name for the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="ec9e7-120">コメント</span><span class="sxs-lookup"><span data-stu-id="ec9e7-120">Remarks</span></span>

<span data-ttu-id="ec9e7-121">継承によって関連付けられているオブジェクトのセットなどの 1 つの名前を使用して参照する関連のオブジェクトのセットがある場合は、選択範囲のセットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ec9e7-121">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="ec9e7-122">ビューを定義するときに、それぞれのビュー内のすべてのオブジェクトを一覧表示するのではなく設定の選択範囲の名前を使用してオブジェクトのセットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ec9e7-122">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="ec9e7-123">一般的な選択範囲のセットは、書式設定ファイルのビューを定義するときに、名前によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="ec9e7-123">Common selection sets are specified by their name when defining the views of the formatting file.</span></span> <span data-ttu-id="ec9e7-124">このような場合、`SelectionSetName`の子要素、`ViewSelectedBy`ビューの要素がセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="ec9e7-124">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` element for the view specifies the set.</span></span> <span data-ttu-id="ec9e7-125">ただし、ビューのさまざまなエントリは、ビューのエントリのみに適用される選択セットも指定できます。</span><span class="sxs-lookup"><span data-stu-id="ec9e7-125">However, different entries of a view can also specify a selection set that applies to only that entry of the view.</span></span> <span data-ttu-id="ec9e7-126">選択範囲のセットの詳細については、[オブジェクト設定を定義する](./defining-selection-sets.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec9e7-126">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="ec9e7-127">例</span><span class="sxs-lookup"><span data-stu-id="ec9e7-127">Example</span></span>

<span data-ttu-id="ec9e7-128">次の例は、 `SelectionSet` 4 つの .NET 型を定義する要素。</span><span class="sxs-lookup"><span data-stu-id="ec9e7-128">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="ec9e7-129">参照</span><span class="sxs-lookup"><span data-stu-id="ec9e7-129">See Also</span></span>

[<span data-ttu-id="ec9e7-130">選択範囲のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="ec9e7-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="ec9e7-131">SelectionSet 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ec9e7-131">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="ec9e7-132">SelectionSets 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ec9e7-132">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="ec9e7-133">型の要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="ec9e7-133">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="ec9e7-134">Windows PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="ec9e7-134">Writing a Windows PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
