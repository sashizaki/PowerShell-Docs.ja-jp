---
title: SelectionSet の Types 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4606fec0-ff31-4d36-af68-227405335ec3
caps.latest.revision: 15
ms.openlocfilehash: 0427367efa2c8a7e352d718706d1341a0c8e3621
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367961"
---
# <a name="types-element-for-selectionset-format"></a><span data-ttu-id="1d7cf-102">SelectionSet の Types 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1d7cf-102">Types Element for SelectionSet (Format)</span></span>

<span data-ttu-id="1d7cf-103">選択セット内の .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="1d7cf-103">Defines the .NET objects that are in the selection set.</span></span>

<span data-ttu-id="1d7cf-104">Configuration 要素 (Format) SelectionSets 要素 (書式) Selectionsets Element (format) Types 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="1d7cf-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1d7cf-105">構文</span><span class="sxs-lookup"><span data-stu-id="1d7cf-105">Syntax</span></span>

```xml
<Types>
  <TypeName>Nameof.NetType</TypeName>
</Types>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="1d7cf-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="1d7cf-106">Attributes and Elements</span></span>

<span data-ttu-id="1d7cf-107">次のセクションでは、`Types` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d7cf-107">The following sections describe the attributes, child elements, and the parent element of the `Types` element.</span></span> <span data-ttu-id="1d7cf-108">少なくとも1つの子要素が必要ですが、追加できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="1d7cf-108">There must be at least one child element, but there is no maximum limit to the number of child elements that can be added.</span></span>

### <a name="attributes"></a><span data-ttu-id="1d7cf-109">属性</span><span class="sxs-lookup"><span data-stu-id="1d7cf-109">Attributes</span></span>

<span data-ttu-id="1d7cf-110">なし。</span><span class="sxs-lookup"><span data-stu-id="1d7cf-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1d7cf-111">子要素</span><span class="sxs-lookup"><span data-stu-id="1d7cf-111">Child Elements</span></span>

|<span data-ttu-id="1d7cf-112">要素</span><span class="sxs-lookup"><span data-stu-id="1d7cf-112">Element</span></span>|<span data-ttu-id="1d7cf-113">説明</span><span class="sxs-lookup"><span data-stu-id="1d7cf-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1d7cf-114">型の TypeName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="1d7cf-114">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)|<span data-ttu-id="1d7cf-115">必須の要素です。</span><span class="sxs-lookup"><span data-stu-id="1d7cf-115">Required element.</span></span><br /><br /> <span data-ttu-id="1d7cf-116">選択セットに属する .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="1d7cf-116">Specifies the .NET object that belongs to the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1d7cf-117">親要素</span><span class="sxs-lookup"><span data-stu-id="1d7cf-117">Parent Elements</span></span>

|<span data-ttu-id="1d7cf-118">要素</span><span class="sxs-lookup"><span data-stu-id="1d7cf-118">Element</span></span>|<span data-ttu-id="1d7cf-119">説明</span><span class="sxs-lookup"><span data-stu-id="1d7cf-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1d7cf-120">SelectionSet 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="1d7cf-120">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="1d7cf-121">セットの名前で参照できる .NET オブジェクトのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="1d7cf-121">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1d7cf-122">コメント</span><span class="sxs-lookup"><span data-stu-id="1d7cf-122">Remarks</span></span>

<span data-ttu-id="1d7cf-123">この要素によって定義されるオブジェクトは、ビューで使用できる選択セット、ビューの定義 (ビューは複数の定義を持つことができます)、または選択条件を指定するときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="1d7cf-123">The objects defined by this element make up a selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span>  <span data-ttu-id="1d7cf-124">選択セットの詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d7cf-124">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="1d7cf-125">例</span><span class="sxs-lookup"><span data-stu-id="1d7cf-125">Example</span></span>

<span data-ttu-id="1d7cf-126">この例は、4つの .NET 型を定義する `SelectionSet` 要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="1d7cf-126">This example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1d7cf-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d7cf-127">See Also</span></span>

[<span data-ttu-id="1d7cf-128">オブジェクトのセットの定義</span><span class="sxs-lookup"><span data-stu-id="1d7cf-128">Defining Sets of Objects</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="1d7cf-129">SelectionSet 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="1d7cf-129">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="1d7cf-130">型の TypeName 要素 (Format)</span><span class="sxs-lookup"><span data-stu-id="1d7cf-130">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)

[<span data-ttu-id="1d7cf-131">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="1d7cf-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
