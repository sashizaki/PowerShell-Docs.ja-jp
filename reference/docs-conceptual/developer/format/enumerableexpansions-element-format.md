---
ms.date: 09/13/2016
ms.topic: reference
title: EnumerableExpansions 要素 (書式)
description: EnumerableExpansions 要素 (書式)
ms.openlocfilehash: 789599e6ff368b4685c7937d5b6eb38618752f9e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660178"
---
# <a name="enumerableexpansions-element-format"></a><span data-ttu-id="905a6-103">EnumerableExpansions 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="905a6-103">EnumerableExpansions Element (Format)</span></span>

<span data-ttu-id="905a6-104">.NET コレクションオブジェクトがビューに表示されるときの展開方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="905a6-104">Defines how .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="905a6-105">Configuration 要素 (Format) DefaultSettings 要素 (Format) 列挙 Able展開要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="905a6-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="905a6-106">構文</span><span class="sxs-lookup"><span data-stu-id="905a6-106">Syntax</span></span>

```xml
<EnumerableExpansions>
  <EnumerableExpansion>...</EnumerableExpansion>
</EnumerableExpansions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="905a6-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="905a6-107">Attributes and Elements</span></span>

<span data-ttu-id="905a6-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `EnumerableExpansions` ます。</span><span class="sxs-lookup"><span data-stu-id="905a6-108">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansions` element.</span></span> <span data-ttu-id="905a6-109">使用できる子要素の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="905a6-109">There is no limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="905a6-110">属性</span><span class="sxs-lookup"><span data-stu-id="905a6-110">Attributes</span></span>

<span data-ttu-id="905a6-111">なし。</span><span class="sxs-lookup"><span data-stu-id="905a6-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="905a6-112">子要素</span><span class="sxs-lookup"><span data-stu-id="905a6-112">Child Elements</span></span>

|<span data-ttu-id="905a6-113">要素</span><span class="sxs-lookup"><span data-stu-id="905a6-113">Element</span></span>|<span data-ttu-id="905a6-114">説明</span><span class="sxs-lookup"><span data-stu-id="905a6-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="905a6-115">EnumerableExpansion 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="905a6-115">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="905a6-116">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="905a6-116">Optional element.</span></span><br /><br /> <span data-ttu-id="905a6-117">ビューに表示されるときに展開される特定の .NET コレクションオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="905a6-117">Defines the specific .NET collection objects that are expanded when they are displayed in a view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="905a6-118">親要素</span><span class="sxs-lookup"><span data-stu-id="905a6-118">Parent Elements</span></span>

|<span data-ttu-id="905a6-119">要素</span><span class="sxs-lookup"><span data-stu-id="905a6-119">Element</span></span>|<span data-ttu-id="905a6-120">説明</span><span class="sxs-lookup"><span data-stu-id="905a6-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="905a6-121">DefaultSettings 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="905a6-121">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="905a6-122">書式設定ファイルのすべてのビューに適用される共通設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="905a6-122">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="905a6-123">解説</span><span class="sxs-lookup"><span data-stu-id="905a6-123">Remarks</span></span>

<span data-ttu-id="905a6-124">この要素は、コレクションオブジェクトとコレクション内のオブジェクトをどのように表示するかを定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="905a6-124">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="905a6-125">この場合、コレクションオブジェクト  **は、system.string インターフェイスを** サポートする任意のオブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="905a6-125">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="905a6-126">参照</span><span class="sxs-lookup"><span data-stu-id="905a6-126">See Also</span></span>

[<span data-ttu-id="905a6-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="905a6-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
