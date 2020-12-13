---
ms.date: 09/13/2016
ms.topic: reference
title: EnumerableExpansion 要素 (書式)
description: EnumerableExpansion 要素 (書式)
ms.openlocfilehash: 207ad99d5335e99701660159ab77279b55b0b6b5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668016"
---
# <a name="enumerableexpansion-element-format"></a><span data-ttu-id="e6afc-103">EnumerableExpansion 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e6afc-103">EnumerableExpansion Element (Format)</span></span>

<span data-ttu-id="e6afc-104">特定の .NET コレクションオブジェクトをビューに表示するときに展開する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="e6afc-104">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="e6afc-105">Configuration 要素 (Format) DefaultSettings 要素 (Format) Enumerableexpansions 要素 (format) の列挙 Ablesize 拡張要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="e6afc-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e6afc-106">構文</span><span class="sxs-lookup"><span data-stu-id="e6afc-106">Syntax</span></span>

```xml
<EnumerableExpansion>
  <EntrySelectedBy>...</EntrySelectedBy>
  <Expand>EnumOnly, CoreOnly, Both</Expand>
</EnumerableExpansion>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e6afc-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e6afc-107">Attributes and Elements</span></span>

<span data-ttu-id="e6afc-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `EnumerableExpansion` ます。</span><span class="sxs-lookup"><span data-stu-id="e6afc-108">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansion` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e6afc-109">属性</span><span class="sxs-lookup"><span data-stu-id="e6afc-109">Attributes</span></span>

<span data-ttu-id="e6afc-110">なし。</span><span class="sxs-lookup"><span data-stu-id="e6afc-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e6afc-111">子要素</span><span class="sxs-lookup"><span data-stu-id="e6afc-111">Child Elements</span></span>

|<span data-ttu-id="e6afc-112">要素</span><span class="sxs-lookup"><span data-stu-id="e6afc-112">Element</span></span>|<span data-ttu-id="e6afc-113">説明</span><span class="sxs-lookup"><span data-stu-id="e6afc-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e6afc-114">EnumerableExpansion の EntrySelectedBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e6afc-114">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="e6afc-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="e6afc-115">Optional element.</span></span><br /><br /> <span data-ttu-id="e6afc-116">この定義によって展開される .NET コレクションオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="e6afc-116">Defines which .NET collection objects are expanded by this definition.</span></span>|
|[<span data-ttu-id="e6afc-117">Expand 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e6afc-117">Expand Element (Format)</span></span>](./expand-element-format.md)|<span data-ttu-id="e6afc-118">この定義に対してコレクションオブジェクトを展開する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="e6afc-118">Specifies how the collection object is expanded for this definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e6afc-119">親要素</span><span class="sxs-lookup"><span data-stu-id="e6afc-119">Parent Elements</span></span>

|<span data-ttu-id="e6afc-120">要素</span><span class="sxs-lookup"><span data-stu-id="e6afc-120">Element</span></span>|<span data-ttu-id="e6afc-121">説明</span><span class="sxs-lookup"><span data-stu-id="e6afc-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e6afc-122">EnumerableExpansions 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e6afc-122">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="e6afc-123">ビューに表示される .NET コレクションオブジェクトを拡張するさまざまな方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="e6afc-123">Defines the different ways that .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e6afc-124">解説</span><span class="sxs-lookup"><span data-stu-id="e6afc-124">Remarks</span></span>

<span data-ttu-id="e6afc-125">この要素は、コレクションオブジェクトとコレクション内のオブジェクトをどのように表示するかを定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e6afc-125">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="e6afc-126">この場合、コレクションオブジェクト  **は、system.string インターフェイスを** サポートする任意のオブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="e6afc-126">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="e6afc-127">既定の動作では、コレクション内のオブジェクトのプロパティのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6afc-127">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6afc-128">参照</span><span class="sxs-lookup"><span data-stu-id="e6afc-128">See Also</span></span>

[<span data-ttu-id="e6afc-129">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="e6afc-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
