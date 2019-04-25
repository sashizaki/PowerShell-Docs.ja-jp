---
title: 要素 (形式) の展開 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: faa0314b-f6f1-44fd-ad2b-b00cbe38923f
caps.latest.revision: 9
ms.openlocfilehash: 8b924c989133b47e4d95d8429778003c76595d58
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066007"
---
# <a name="expand-element-format"></a><span data-ttu-id="7e0a5-102">Expand 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="7e0a5-102">Expand Element (Format)</span></span>

<span data-ttu-id="7e0a5-103">この定義のコレクション オブジェクトを展開する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="7e0a5-103">Specifies how the collection object is expanded for this definition.</span></span>

<span data-ttu-id="7e0a5-104">要素 (形式) を展開する構成要素 (形式) DefaultSettings 要素 (形式) EnumerableExpansions 要素 (形式) EnumerableExpansion 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7e0a5-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) Expand Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7e0a5-105">構文</span><span class="sxs-lookup"><span data-stu-id="7e0a5-105">Syntax</span></span>

```xml
<Expand>EnumOnly, CoreOnly, Both</Expand>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7e0a5-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7e0a5-106">Attributes and Elements</span></span>

<span data-ttu-id="7e0a5-107">次のセクションでは、属性、子要素、およびの親要素について説明します、`Expand`要素。</span><span class="sxs-lookup"><span data-stu-id="7e0a5-107">The following sections describe attributes, child elements, and the parent element of the `Expand` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7e0a5-108">属性</span><span class="sxs-lookup"><span data-stu-id="7e0a5-108">Attributes</span></span>

<span data-ttu-id="7e0a5-109">なし。</span><span class="sxs-lookup"><span data-stu-id="7e0a5-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7e0a5-110">子要素</span><span class="sxs-lookup"><span data-stu-id="7e0a5-110">Child Elements</span></span>

<span data-ttu-id="7e0a5-111">なし。</span><span class="sxs-lookup"><span data-stu-id="7e0a5-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7e0a5-112">親要素</span><span class="sxs-lookup"><span data-stu-id="7e0a5-112">Parent Elements</span></span>

|<span data-ttu-id="7e0a5-113">要素</span><span class="sxs-lookup"><span data-stu-id="7e0a5-113">Element</span></span>|<span data-ttu-id="7e0a5-114">説明</span><span class="sxs-lookup"><span data-stu-id="7e0a5-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7e0a5-115">EnumerableExpansion 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="7e0a5-115">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="7e0a5-116">ビューに表示されているときに、オブジェクトが展開されます、特定の .NET コレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="7e0a5-116">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7e0a5-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="7e0a5-117">Text Value</span></span>

<span data-ttu-id="7e0a5-118">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="7e0a5-118">Specify one of the following values:</span></span>

- <span data-ttu-id="7e0a5-119">Enumonly です。コレクション内のオブジェクトのプロパティのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="7e0a5-119">EnumOnly: Displays only the properties of the objects in the collection.</span></span>

- <span data-ttu-id="7e0a5-120">CoreOnly:コレクション オブジェクトのプロパティのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e0a5-120">CoreOnly: Displays only the properties of the collection object.</span></span>

- <span data-ttu-id="7e0a5-121">両方とも：コレクションおよびコレクション オブジェクトのプロパティのオブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="7e0a5-121">Both: Displays the properties of the objects in the collection and the properties of the collection object.</span></span>

## <a name="remarks"></a><span data-ttu-id="7e0a5-122">コメント</span><span class="sxs-lookup"><span data-stu-id="7e0a5-122">Remarks</span></span>

<span data-ttu-id="7e0a5-123">この要素を使用して、コレクション オブジェクトと、コレクション内のオブジェクトを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="7e0a5-123">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="7e0a5-124">コレクション オブジェクトをサポートする任意のオブジェクトを指すここで、 **System.Collections.ICollection**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="7e0a5-124">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="7e0a5-125">既定の動作では、コレクション内のオブジェクトのプロパティのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="7e0a5-125">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e0a5-126">参照</span><span class="sxs-lookup"><span data-stu-id="7e0a5-126">See Also</span></span>

[<span data-ttu-id="7e0a5-127">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="7e0a5-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
