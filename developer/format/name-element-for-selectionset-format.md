---
title: SelectionSet (形式) の要素の名前を付けます |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 914917f7-0efc-4d1f-88bd-de714bedd98f
caps.latest.revision: 15
ms.openlocfilehash: 29dbdbd335511e4ca2706a625541554825838f23
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858168"
---
# <a name="name-element-for-selectionset-format"></a><span data-ttu-id="7c44c-102">SelectionSet の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7c44c-102">Name Element for SelectionSet (Format)</span></span>

<span data-ttu-id="7c44c-103">選択範囲のセットを参照するための名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c44c-103">Specifies the name used to reference the selection set.</span></span>

<span data-ttu-id="7c44c-104">SelectionSet (形式) の構成要素 (形式) SelectionSets 要素 (形式) SelectionSet 要素 (形式) の名前要素</span><span class="sxs-lookup"><span data-stu-id="7c44c-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Name Element of SelectionSet (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7c44c-105">構文</span><span class="sxs-lookup"><span data-stu-id="7c44c-105">Syntax</span></span>

```xml
<Name>Name of selection set</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7c44c-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="7c44c-106">Attributes and Elements</span></span>

<span data-ttu-id="7c44c-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`Name`要素。</span><span class="sxs-lookup"><span data-stu-id="7c44c-107">The following sections describe the attributes, child elements, and parent element of the `Name` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7c44c-108">属性</span><span class="sxs-lookup"><span data-stu-id="7c44c-108">Attributes</span></span>

<span data-ttu-id="7c44c-109">なし。</span><span class="sxs-lookup"><span data-stu-id="7c44c-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7c44c-110">子要素</span><span class="sxs-lookup"><span data-stu-id="7c44c-110">Child Elements</span></span>

<span data-ttu-id="7c44c-111">なし。</span><span class="sxs-lookup"><span data-stu-id="7c44c-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7c44c-112">親要素</span><span class="sxs-lookup"><span data-stu-id="7c44c-112">Parent Elements</span></span>

|<span data-ttu-id="7c44c-113">要素</span><span class="sxs-lookup"><span data-stu-id="7c44c-113">Element</span></span>|<span data-ttu-id="7c44c-114">説明</span><span class="sxs-lookup"><span data-stu-id="7c44c-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7c44c-115">SelectionSet 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7c44c-115">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="7c44c-116">セットの名前で参照できる .NET オブジェクトの 1 つのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="7c44c-116">Defines a single set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7c44c-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="7c44c-117">Text Value</span></span>

<span data-ttu-id="7c44c-118">選択範囲のセットを参照する名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c44c-118">Specify the name to reference the selection set.</span></span> <span data-ttu-id="7c44c-119">どのような文字に関する制限は使用できません。</span><span class="sxs-lookup"><span data-stu-id="7c44c-119">There are no restrictions as to what characters can be used.</span></span>

## <a name="remarks"></a><span data-ttu-id="7c44c-120">コメント</span><span class="sxs-lookup"><span data-stu-id="7c44c-120">Remarks</span></span>

<span data-ttu-id="7c44c-121">ここで指定した名前で使用されます、`SelectionSetName`要素。</span><span class="sxs-lookup"><span data-stu-id="7c44c-121">The name specified here is used in the `SelectionSetName` element.</span></span> <span data-ttu-id="7c44c-122">ビューの定義によって、ビューで使用できる選択セット (ビューが複数の定義を持つ) は、選択条件を指定する場合またはします。</span><span class="sxs-lookup"><span data-stu-id="7c44c-122">The selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span> <span data-ttu-id="7c44c-123">選択範囲のセットの詳細については、[オブジェクト設定を定義する](./defining-selection-sets.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c44c-123">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="7c44c-124">例</span><span class="sxs-lookup"><span data-stu-id="7c44c-124">Example</span></span>

<span data-ttu-id="7c44c-125">この例では、 `SelectionSet` 4 つの .NET 型を定義する要素。</span><span class="sxs-lookup"><span data-stu-id="7c44c-125">This example shows a `SelectionSet` element that defines four .NET types.</span></span> <span data-ttu-id="7c44c-126">選択範囲のセットの名前は、"FileSystemTypes"です。</span><span class="sxs-lookup"><span data-stu-id="7c44c-126">The name of the selection set is "FileSystemTypes".</span></span>

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

## <a name="see-also"></a><span data-ttu-id="7c44c-127">参照</span><span class="sxs-lookup"><span data-stu-id="7c44c-127">See Also</span></span>

[<span data-ttu-id="7c44c-128">選択範囲のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="7c44c-128">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="7c44c-129">SelectionSet 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7c44c-129">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="7c44c-130">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="7c44c-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
