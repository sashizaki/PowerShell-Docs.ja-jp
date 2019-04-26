---
title: EnumerableExpansion 要素 (式) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93d27173-9ae4-46e5-bb78-90525915cd70
caps.latest.revision: 9
ms.openlocfilehash: bc1e58c00ca8419f9204076f0a46050281e704db
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066143"
---
# <a name="enumerableexpansion-element-format"></a><span data-ttu-id="d34bc-102">EnumerableExpansion 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d34bc-102">EnumerableExpansion Element (Format)</span></span>

<span data-ttu-id="d34bc-103">ビューに表示されているときに、オブジェクトが展開されます、特定の .NET コレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="d34bc-103">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="d34bc-104">構成要素 (形式) DefaultSettings 要素 (形式) EnumerableExpansions 要素 (形式) EnumerableExpansion 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="d34bc-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d34bc-105">構文</span><span class="sxs-lookup"><span data-stu-id="d34bc-105">Syntax</span></span>

```xml
<EnumerableExpansion>
  <EntrySelectedBy>...</EntrySelectedBy>
  <Expand>EnumOnly, CoreOnly, Both</Expand>
</EnumerableExpansion>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d34bc-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d34bc-106">Attributes and Elements</span></span>

<span data-ttu-id="d34bc-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`EnumerableExpansion`要素。</span><span class="sxs-lookup"><span data-stu-id="d34bc-107">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansion` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d34bc-108">属性</span><span class="sxs-lookup"><span data-stu-id="d34bc-108">Attributes</span></span>

<span data-ttu-id="d34bc-109">なし。</span><span class="sxs-lookup"><span data-stu-id="d34bc-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d34bc-110">子要素</span><span class="sxs-lookup"><span data-stu-id="d34bc-110">Child Elements</span></span>

|<span data-ttu-id="d34bc-111">要素</span><span class="sxs-lookup"><span data-stu-id="d34bc-111">Element</span></span>|<span data-ttu-id="d34bc-112">説明</span><span class="sxs-lookup"><span data-stu-id="d34bc-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d34bc-113">EnumerableExpansion (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="d34bc-113">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="d34bc-114">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d34bc-114">Optional element.</span></span><br /><br /> <span data-ttu-id="d34bc-115">.NET コレクション オブジェクトの拡張機能では、この定義を定義します。</span><span class="sxs-lookup"><span data-stu-id="d34bc-115">Defines which .NET collection objects are expanded by this definition.</span></span>|
|[<span data-ttu-id="d34bc-116">要素 (形式) の展開します。</span><span class="sxs-lookup"><span data-stu-id="d34bc-116">Expand Element (Format)</span></span>](./expand-element-format.md)|<span data-ttu-id="d34bc-117">この定義のコレクション オブジェクトを展開する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="d34bc-117">Specifies how the collection object is expanded for this definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d34bc-118">親要素</span><span class="sxs-lookup"><span data-stu-id="d34bc-118">Parent Elements</span></span>

|<span data-ttu-id="d34bc-119">要素</span><span class="sxs-lookup"><span data-stu-id="d34bc-119">Element</span></span>|<span data-ttu-id="d34bc-120">説明</span><span class="sxs-lookup"><span data-stu-id="d34bc-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d34bc-121">EnumerableExpansions 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="d34bc-121">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="d34bc-122">オブジェクトは、ビューに表示されているときに展開されますが、その .NET コレクションにさまざまな方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="d34bc-122">Defines the different ways that .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d34bc-123">コメント</span><span class="sxs-lookup"><span data-stu-id="d34bc-123">Remarks</span></span>

<span data-ttu-id="d34bc-124">この要素を使用して、コレクション オブジェクトと、コレクション内のオブジェクトを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="d34bc-124">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="d34bc-125">コレクション オブジェクトをサポートする任意のオブジェクトを指すここで、 **System.Collections.ICollection**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="d34bc-125">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="d34bc-126">既定の動作では、コレクション内のオブジェクトのプロパティのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="d34bc-126">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="d34bc-127">参照</span><span class="sxs-lookup"><span data-stu-id="d34bc-127">See Also</span></span>

[<span data-ttu-id="d34bc-128">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="d34bc-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
