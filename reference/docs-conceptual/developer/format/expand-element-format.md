---
title: Expand 要素 (Format) |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: faa0314b-f6f1-44fd-ad2b-b00cbe38923f
caps.latest.revision: 9
ms.openlocfilehash: 8b924c989133b47e4d95d8429778003c76595d58
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368741"
---
# <a name="expand-element-format"></a><span data-ttu-id="87b2b-102">Expand 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="87b2b-102">Expand Element (Format)</span></span>

<span data-ttu-id="87b2b-103">この定義に対してコレクションオブジェクトを展開する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="87b2b-103">Specifies how the collection object is expanded for this definition.</span></span>

<span data-ttu-id="87b2b-104">Configuration 要素 (Format) DefaultSettings 要素 (Format) 列挙 Ableexpand 要素 (format) 列挙 Ableexpand 要素 (format) Expand 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="87b2b-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) Expand Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="87b2b-105">構文</span><span class="sxs-lookup"><span data-stu-id="87b2b-105">Syntax</span></span>

```xml
<Expand>EnumOnly, CoreOnly, Both</Expand>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="87b2b-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="87b2b-106">Attributes and Elements</span></span>

<span data-ttu-id="87b2b-107">次のセクションでは、属性、子要素、`Expand` 要素の親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="87b2b-107">The following sections describe attributes, child elements, and the parent element of the `Expand` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="87b2b-108">属性</span><span class="sxs-lookup"><span data-stu-id="87b2b-108">Attributes</span></span>

<span data-ttu-id="87b2b-109">なし。</span><span class="sxs-lookup"><span data-stu-id="87b2b-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="87b2b-110">子要素</span><span class="sxs-lookup"><span data-stu-id="87b2b-110">Child Elements</span></span>

<span data-ttu-id="87b2b-111">なし。</span><span class="sxs-lookup"><span data-stu-id="87b2b-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="87b2b-112">親要素</span><span class="sxs-lookup"><span data-stu-id="87b2b-112">Parent Elements</span></span>

|<span data-ttu-id="87b2b-113">要素</span><span class="sxs-lookup"><span data-stu-id="87b2b-113">Element</span></span>|<span data-ttu-id="87b2b-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="87b2b-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="87b2b-115">列挙 Able展開要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="87b2b-115">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="87b2b-116">特定の .NET コレクションオブジェクトをビューに表示するときに展開する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="87b2b-116">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="87b2b-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="87b2b-117">Text Value</span></span>

<span data-ttu-id="87b2b-118">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="87b2b-118">Specify one of the following values:</span></span>

- <span data-ttu-id="87b2b-119">EnumOnly: コレクション内のオブジェクトのプロパティのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="87b2b-119">EnumOnly: Displays only the properties of the objects in the collection.</span></span>

- <span data-ttu-id="87b2b-120">CoreOnly: コレクションオブジェクトのプロパティのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="87b2b-120">CoreOnly: Displays only the properties of the collection object.</span></span>

- <span data-ttu-id="87b2b-121">Both: コレクション内のオブジェクトのプロパティと、コレクションオブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="87b2b-121">Both: Displays the properties of the objects in the collection and the properties of the collection object.</span></span>

## <a name="remarks"></a><span data-ttu-id="87b2b-122">コメント</span><span class="sxs-lookup"><span data-stu-id="87b2b-122">Remarks</span></span>

<span data-ttu-id="87b2b-123">この要素は、コレクションオブジェクトとコレクション内のオブジェクトをどのように表示するかを定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="87b2b-123">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="87b2b-124">この場合、コレクションオブジェクト**は、system.string インターフェイスを**サポートする任意のオブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="87b2b-124">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="87b2b-125">既定の動作では、コレクション内のオブジェクトのプロパティのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87b2b-125">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="87b2b-126">参照</span><span class="sxs-lookup"><span data-stu-id="87b2b-126">See Also</span></span>

[<span data-ttu-id="87b2b-127">PowerShell フォーマットファイルの作成</span><span class="sxs-lookup"><span data-stu-id="87b2b-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
