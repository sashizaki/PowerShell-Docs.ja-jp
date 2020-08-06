---
title: Expand 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: deee832254bb8a774ee2c1f5bd451d3ced1bd47a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783655"
---
# <a name="expand-element-format"></a><span data-ttu-id="91a47-102">Expand 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="91a47-102">Expand Element (Format)</span></span>

<span data-ttu-id="91a47-103">この定義に対してコレクションオブジェクトを展開する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="91a47-103">Specifies how the collection object is expanded for this definition.</span></span>

<span data-ttu-id="91a47-104">Configuration 要素 (Format) DefaultSettings 要素 (Format) 列挙 Ableexpand 要素 (format) 列挙 Ableexpand 要素 (format) Expand 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="91a47-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) Expand Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="91a47-105">構文</span><span class="sxs-lookup"><span data-stu-id="91a47-105">Syntax</span></span>

```xml
<Expand>EnumOnly, CoreOnly, Both</Expand>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="91a47-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="91a47-106">Attributes and Elements</span></span>

<span data-ttu-id="91a47-107">次のセクションでは、要素の属性、子要素、および親要素について説明し `Expand` ます。</span><span class="sxs-lookup"><span data-stu-id="91a47-107">The following sections describe attributes, child elements, and the parent element of the `Expand` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="91a47-108">属性</span><span class="sxs-lookup"><span data-stu-id="91a47-108">Attributes</span></span>

<span data-ttu-id="91a47-109">なし。</span><span class="sxs-lookup"><span data-stu-id="91a47-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="91a47-110">子要素</span><span class="sxs-lookup"><span data-stu-id="91a47-110">Child Elements</span></span>

<span data-ttu-id="91a47-111">なし。</span><span class="sxs-lookup"><span data-stu-id="91a47-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="91a47-112">親要素</span><span class="sxs-lookup"><span data-stu-id="91a47-112">Parent Elements</span></span>

|<span data-ttu-id="91a47-113">要素</span><span class="sxs-lookup"><span data-stu-id="91a47-113">Element</span></span>|<span data-ttu-id="91a47-114">説明</span><span class="sxs-lookup"><span data-stu-id="91a47-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="91a47-115">EnumerableExpansion 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="91a47-115">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="91a47-116">特定の .NET コレクションオブジェクトをビューに表示するときに展開する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="91a47-116">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="91a47-117">テキスト値</span><span class="sxs-lookup"><span data-stu-id="91a47-117">Text Value</span></span>

<span data-ttu-id="91a47-118">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="91a47-118">Specify one of the following values:</span></span>

- <span data-ttu-id="91a47-119">EnumOnly: コレクション内のオブジェクトのプロパティのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="91a47-119">EnumOnly: Displays only the properties of the objects in the collection.</span></span>

- <span data-ttu-id="91a47-120">CoreOnly: コレクションオブジェクトのプロパティのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="91a47-120">CoreOnly: Displays only the properties of the collection object.</span></span>

- <span data-ttu-id="91a47-121">Both: コレクション内のオブジェクトのプロパティと、コレクションオブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="91a47-121">Both: Displays the properties of the objects in the collection and the properties of the collection object.</span></span>

## <a name="remarks"></a><span data-ttu-id="91a47-122">解説</span><span class="sxs-lookup"><span data-stu-id="91a47-122">Remarks</span></span>

<span data-ttu-id="91a47-123">この要素は、コレクションオブジェクトとコレクション内のオブジェクトをどのように表示するかを定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="91a47-123">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="91a47-124">この場合、コレクションオブジェクト**は、system.string インターフェイスを**サポートする任意のオブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="91a47-124">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="91a47-125">既定の動作では、コレクション内のオブジェクトのプロパティのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="91a47-125">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="91a47-126">参照</span><span class="sxs-lookup"><span data-stu-id="91a47-126">See Also</span></span>

[<span data-ttu-id="91a47-127">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="91a47-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
