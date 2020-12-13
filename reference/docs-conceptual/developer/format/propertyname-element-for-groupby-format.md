---
ms.date: 09/13/2016
ms.topic: reference
title: GroupBy の PropertyName 要素 (書式)
description: GroupBy の PropertyName 要素 (書式)
ms.openlocfilehash: 44351c46ff2386f967644fef4f423b3858dc1619
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666146"
---
# <a name="propertyname-element-for-groupby-format"></a><span data-ttu-id="44da9-103">GroupBy の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="44da9-103">PropertyName Element for GroupBy (Format)</span></span>

<span data-ttu-id="44da9-104">値が変更されるたびに新しいグループを開始する .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="44da9-104">Specifies the .NET property that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="44da9-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビューの要素 (書式) GroupBy 要素 (形式) の PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="44da9-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) PropertyName Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="44da9-106">構文</span><span class="sxs-lookup"><span data-stu-id="44da9-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="44da9-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="44da9-107">Attributes and Elements</span></span>

<span data-ttu-id="44da9-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="44da9-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="44da9-109">属性</span><span class="sxs-lookup"><span data-stu-id="44da9-109">Attributes</span></span>

<span data-ttu-id="44da9-110">なし。</span><span class="sxs-lookup"><span data-stu-id="44da9-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="44da9-111">子要素</span><span class="sxs-lookup"><span data-stu-id="44da9-111">Child Elements</span></span>

<span data-ttu-id="44da9-112">なし。</span><span class="sxs-lookup"><span data-stu-id="44da9-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="44da9-113">親要素</span><span class="sxs-lookup"><span data-stu-id="44da9-113">Parent Elements</span></span>

|<span data-ttu-id="44da9-114">要素</span><span class="sxs-lookup"><span data-stu-id="44da9-114">Element</span></span>|<span data-ttu-id="44da9-115">説明</span><span class="sxs-lookup"><span data-stu-id="44da9-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="44da9-116">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="44da9-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="44da9-117">.NET オブジェクトのグループを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="44da9-117">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="44da9-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="44da9-118">Text Value</span></span>

<span data-ttu-id="44da9-119">.NET プロパティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="44da9-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="44da9-120">解説</span><span class="sxs-lookup"><span data-stu-id="44da9-120">Remarks</span></span>

<span data-ttu-id="44da9-121">このプロパティの値が変更されるたびに、Windows PowerShell によって新しいグループが開始されます。</span><span class="sxs-lookup"><span data-stu-id="44da9-121">Windows PowerShell starts a new group whenever the value of this property changes.</span></span>

<span data-ttu-id="44da9-122">この要素が指定されている場合、 [ScriptBlock](./scriptblock-element-for-groupby-format.md) 要素を指定して新しいグループを開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="44da9-122">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="example"></a><span data-ttu-id="44da9-123">例</span><span class="sxs-lookup"><span data-stu-id="44da9-123">Example</span></span>

<span data-ttu-id="44da9-124">次の例は、プロパティの値が変更されたときに新しいグループを開始する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="44da9-124">The following example shows how to start a new group when the value of a property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="44da9-125">この要素を含む完全な書式設定ファイルの例については、「 [Wide ビュー (GroupBy)](./wide-view-groupby.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44da9-125">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="44da9-126">参照</span><span class="sxs-lookup"><span data-stu-id="44da9-126">See Also</span></span>

[<span data-ttu-id="44da9-127">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="44da9-127">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="44da9-128">GroupBy の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="44da9-128">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="44da9-129">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="44da9-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
