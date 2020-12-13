---
ms.date: 09/13/2016
ms.topic: reference
title: Expand 要素 (書式)
description: Expand 要素 (書式)
ms.openlocfilehash: 518e132e3e74b921d4e51966fc60088a22ef63f1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667948"
---
# <a name="expand-element-format"></a><span data-ttu-id="734b2-103">Expand 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="734b2-103">Expand Element (Format)</span></span>

<span data-ttu-id="734b2-104">この定義に対してコレクションオブジェクトを展開する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="734b2-104">Specifies how the collection object is expanded for this definition.</span></span>

<span data-ttu-id="734b2-105">Configuration 要素 (Format) DefaultSettings 要素 (Format) 列挙 Ableexpand 要素 (format) 列挙 Ableexpand 要素 (format) Expand 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="734b2-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) Expand Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="734b2-106">構文</span><span class="sxs-lookup"><span data-stu-id="734b2-106">Syntax</span></span>

```xml
<Expand>EnumOnly, CoreOnly, Both</Expand>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="734b2-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="734b2-107">Attributes and Elements</span></span>

<span data-ttu-id="734b2-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `Expand` ます。</span><span class="sxs-lookup"><span data-stu-id="734b2-108">The following sections describe attributes, child elements, and the parent element of the `Expand` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="734b2-109">属性</span><span class="sxs-lookup"><span data-stu-id="734b2-109">Attributes</span></span>

<span data-ttu-id="734b2-110">なし。</span><span class="sxs-lookup"><span data-stu-id="734b2-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="734b2-111">子要素</span><span class="sxs-lookup"><span data-stu-id="734b2-111">Child Elements</span></span>

<span data-ttu-id="734b2-112">なし。</span><span class="sxs-lookup"><span data-stu-id="734b2-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="734b2-113">親要素</span><span class="sxs-lookup"><span data-stu-id="734b2-113">Parent Elements</span></span>

|<span data-ttu-id="734b2-114">要素</span><span class="sxs-lookup"><span data-stu-id="734b2-114">Element</span></span>|<span data-ttu-id="734b2-115">説明</span><span class="sxs-lookup"><span data-stu-id="734b2-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="734b2-116">EnumerableExpansion 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="734b2-116">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="734b2-117">特定の .NET コレクションオブジェクトをビューに表示するときに展開する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="734b2-117">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="734b2-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="734b2-118">Text Value</span></span>

<span data-ttu-id="734b2-119">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="734b2-119">Specify one of the following values:</span></span>

- <span data-ttu-id="734b2-120">EnumOnly: コレクション内のオブジェクトのプロパティのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="734b2-120">EnumOnly: Displays only the properties of the objects in the collection.</span></span>

- <span data-ttu-id="734b2-121">CoreOnly: コレクションオブジェクトのプロパティのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="734b2-121">CoreOnly: Displays only the properties of the collection object.</span></span>

- <span data-ttu-id="734b2-122">Both: コレクション内のオブジェクトのプロパティと、コレクションオブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="734b2-122">Both: Displays the properties of the objects in the collection and the properties of the collection object.</span></span>

## <a name="remarks"></a><span data-ttu-id="734b2-123">解説</span><span class="sxs-lookup"><span data-stu-id="734b2-123">Remarks</span></span>

<span data-ttu-id="734b2-124">この要素は、コレクションオブジェクトとコレクション内のオブジェクトをどのように表示するかを定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="734b2-124">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="734b2-125">この場合、コレクションオブジェクト  **は、system.string インターフェイスを** サポートする任意のオブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="734b2-125">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="734b2-126">既定の動作では、コレクション内のオブジェクトのプロパティのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="734b2-126">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="734b2-127">参照</span><span class="sxs-lookup"><span data-stu-id="734b2-127">See Also</span></span>

[<span data-ttu-id="734b2-128">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="734b2-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
