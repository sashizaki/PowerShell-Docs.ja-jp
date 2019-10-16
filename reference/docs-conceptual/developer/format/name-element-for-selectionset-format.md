---
title: SelectionSet の Name 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 914917f7-0efc-4d1f-88bd-de714bedd98f
caps.latest.revision: 15
ms.openlocfilehash: 29dbdbd335511e4ca2706a625541554825838f23
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362671"
---
# <a name="name-element-for-selectionset-format"></a><span data-ttu-id="502eb-102">SelectionSet の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="502eb-102">Name Element for SelectionSet (Format)</span></span>

<span data-ttu-id="502eb-103">選択セットを参照するために使用する名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="502eb-103">Specifies the name used to reference the selection set.</span></span>

<span data-ttu-id="502eb-104">Configuration 要素 (Format) SelectionSets 要素 (形式) Selectionsets 要素 (書式) Selectionsets (形式) の名前要素</span><span class="sxs-lookup"><span data-stu-id="502eb-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Name Element of SelectionSet (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="502eb-105">構文</span><span class="sxs-lookup"><span data-stu-id="502eb-105">Syntax</span></span>

```xml
<Name>Name of selection set</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="502eb-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="502eb-106">Attributes and Elements</span></span>

<span data-ttu-id="502eb-107">次のセクションでは、`Name` 要素の属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="502eb-107">The following sections describe the attributes, child elements, and parent element of the `Name` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="502eb-108">属性</span><span class="sxs-lookup"><span data-stu-id="502eb-108">Attributes</span></span>

<span data-ttu-id="502eb-109">なし。</span><span class="sxs-lookup"><span data-stu-id="502eb-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="502eb-110">子要素</span><span class="sxs-lookup"><span data-stu-id="502eb-110">Child Elements</span></span>

<span data-ttu-id="502eb-111">なし。</span><span class="sxs-lookup"><span data-stu-id="502eb-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="502eb-112">親要素</span><span class="sxs-lookup"><span data-stu-id="502eb-112">Parent Elements</span></span>

|<span data-ttu-id="502eb-113">要素</span><span class="sxs-lookup"><span data-stu-id="502eb-113">Element</span></span>|<span data-ttu-id="502eb-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="502eb-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="502eb-115">SelectionSet 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="502eb-115">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="502eb-116">セットの名前で参照できる .NET オブジェクトの1つのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="502eb-116">Defines a single set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="502eb-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="502eb-117">Text Value</span></span>

<span data-ttu-id="502eb-118">選択セットを参照する名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="502eb-118">Specify the name to reference the selection set.</span></span> <span data-ttu-id="502eb-119">使用できる文字に関する制限はありません。</span><span class="sxs-lookup"><span data-stu-id="502eb-119">There are no restrictions as to what characters can be used.</span></span>

## <a name="remarks"></a><span data-ttu-id="502eb-120">コメント</span><span class="sxs-lookup"><span data-stu-id="502eb-120">Remarks</span></span>

<span data-ttu-id="502eb-121">ここで指定された名前は、`SelectionSetName` 要素で使用されます。</span><span class="sxs-lookup"><span data-stu-id="502eb-121">The name specified here is used in the `SelectionSetName` element.</span></span> <span data-ttu-id="502eb-122">ビューで使用できる選択セット (ビューには複数の定義を含めることができます)、または選択条件を指定する場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="502eb-122">The selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span> <span data-ttu-id="502eb-123">選択セットの詳細については、「[オブジェクトのセットの定義](./defining-selection-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="502eb-123">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="502eb-124">例</span><span class="sxs-lookup"><span data-stu-id="502eb-124">Example</span></span>

<span data-ttu-id="502eb-125">この例は、4つの .NET 型を定義する @no__t 0 の要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="502eb-125">This example shows a `SelectionSet` element that defines four .NET types.</span></span> <span data-ttu-id="502eb-126">選択セットの名前は "FileSystemTypes" です。</span><span class="sxs-lookup"><span data-stu-id="502eb-126">The name of the selection set is "FileSystemTypes".</span></span>

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

## <a name="see-also"></a><span data-ttu-id="502eb-127">参照</span><span class="sxs-lookup"><span data-stu-id="502eb-127">See Also</span></span>

[<span data-ttu-id="502eb-128">選択セットの定義</span><span class="sxs-lookup"><span data-stu-id="502eb-128">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="502eb-129">SelectionSet 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="502eb-129">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="502eb-130">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="502eb-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
