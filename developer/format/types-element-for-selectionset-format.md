---
title: SelectionSet (形式) の要素の種類 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4606fec0-ff31-4d36-af68-227405335ec3
caps.latest.revision: 15
ms.openlocfilehash: 0427367efa2c8a7e352d718706d1341a0c8e3621
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862378"
---
# <a name="types-element-for-selectionset-format"></a><span data-ttu-id="deb7a-102">SelectionSet の Types 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="deb7a-102">Types Element for SelectionSet (Format)</span></span>

<span data-ttu-id="deb7a-103">選択範囲で設定された .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="deb7a-103">Defines the .NET objects that are in the selection set.</span></span>

<span data-ttu-id="deb7a-104">構成要素 (形式) SelectionSets 要素 (形式) SelectionSet 要素 (形式) 型の要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="deb7a-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="deb7a-105">構文</span><span class="sxs-lookup"><span data-stu-id="deb7a-105">Syntax</span></span>

```xml
<Types>
  <TypeName>Nameof.NetType</TypeName>
</Types>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="deb7a-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="deb7a-106">Attributes and Elements</span></span>

<span data-ttu-id="deb7a-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`Types`要素。</span><span class="sxs-lookup"><span data-stu-id="deb7a-107">The following sections describe the attributes, child elements, and the parent element of the `Types` element.</span></span> <span data-ttu-id="deb7a-108">少なくとも 1 つの子要素がありますが、追加できる子要素の数に上限はありません。</span><span class="sxs-lookup"><span data-stu-id="deb7a-108">There must be at least one child element, but there is no maximum limit to the number of child elements that can be added.</span></span>

### <a name="attributes"></a><span data-ttu-id="deb7a-109">属性</span><span class="sxs-lookup"><span data-stu-id="deb7a-109">Attributes</span></span>

<span data-ttu-id="deb7a-110">なし。</span><span class="sxs-lookup"><span data-stu-id="deb7a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="deb7a-111">子要素</span><span class="sxs-lookup"><span data-stu-id="deb7a-111">Child Elements</span></span>

|<span data-ttu-id="deb7a-112">要素</span><span class="sxs-lookup"><span data-stu-id="deb7a-112">Element</span></span>|<span data-ttu-id="deb7a-113">説明</span><span class="sxs-lookup"><span data-stu-id="deb7a-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="deb7a-114">TypeName 要素の種類 (形式)</span><span class="sxs-lookup"><span data-stu-id="deb7a-114">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)|<span data-ttu-id="deb7a-115">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="deb7a-115">Required element.</span></span><br /><br /> <span data-ttu-id="deb7a-116">選択範囲のセットに属する .NET オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="deb7a-116">Specifies the .NET object that belongs to the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="deb7a-117">親要素</span><span class="sxs-lookup"><span data-stu-id="deb7a-117">Parent Elements</span></span>

|<span data-ttu-id="deb7a-118">要素</span><span class="sxs-lookup"><span data-stu-id="deb7a-118">Element</span></span>|<span data-ttu-id="deb7a-119">説明</span><span class="sxs-lookup"><span data-stu-id="deb7a-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="deb7a-120">SelectionSet 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="deb7a-120">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="deb7a-121">セットの名前で参照できる .NET オブジェクトのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="deb7a-121">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="remarks"></a><span data-ttu-id="deb7a-122">コメント</span><span class="sxs-lookup"><span data-stu-id="deb7a-122">Remarks</span></span>

<span data-ttu-id="deb7a-123">この要素で定義されているオブジェクトがビューの定義によって、ビューで使用できる選択セットを構成する (ビューが複数の定義を持つ) は、選択条件を指定する場合またはします。</span><span class="sxs-lookup"><span data-stu-id="deb7a-123">The objects defined by this element make up a selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span>  <span data-ttu-id="deb7a-124">選択範囲のセットの詳細については、[オブジェクト設定を定義する](./defining-selection-sets.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="deb7a-124">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="deb7a-125">例</span><span class="sxs-lookup"><span data-stu-id="deb7a-125">Example</span></span>

<span data-ttu-id="deb7a-126">この例では、 `SelectionSet` 4 つの .NET 型を定義する要素。</span><span class="sxs-lookup"><span data-stu-id="deb7a-126">This example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="deb7a-127">参照</span><span class="sxs-lookup"><span data-stu-id="deb7a-127">See Also</span></span>

[<span data-ttu-id="deb7a-128">オブジェクトのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="deb7a-128">Defining Sets of Objects</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="deb7a-129">SelectionSet 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="deb7a-129">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="deb7a-130">TypeName 要素の種類 (形式)</span><span class="sxs-lookup"><span data-stu-id="deb7a-130">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)

[<span data-ttu-id="deb7a-131">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="deb7a-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
