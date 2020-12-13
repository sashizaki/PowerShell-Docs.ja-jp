---
ms.date: 09/13/2016
ms.topic: reference
title: GroupBy の CustomControlName 要素 (書式)
description: GroupBy の CustomControlName 要素 (書式)
ms.openlocfilehash: 03664fe4d5559312e2720a3892493c90c15f7501
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655420"
---
# <a name="customcontrolname-element-for-groupby-format"></a><span data-ttu-id="e66cd-103">GroupBy の CustomControlName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e66cd-103">CustomControlName Element for GroupBy (Format)</span></span>

<span data-ttu-id="e66cd-104">新しいグループを表示するために使用されるカスタムコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e66cd-104">Specifies the name of a custom control that is used to display the new group.</span></span> <span data-ttu-id="e66cd-105">この要素は、テーブル、リスト、ワイド、またはカスタムコントロールビューを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e66cd-105">This element is used when defining a table, list, wide or custom control view.</span></span>

<span data-ttu-id="e66cd-106">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) GroupBy 要素 (format) の CustomControlName 要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="e66cd-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControlName Element of GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e66cd-107">構文</span><span class="sxs-lookup"><span data-stu-id="e66cd-107">Syntax</span></span>

```xml
<CustomControlName>ControlName</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e66cd-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e66cd-108">Attributes and Elements</span></span>

<span data-ttu-id="e66cd-109">次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomControlName` ます。</span><span class="sxs-lookup"><span data-stu-id="e66cd-109">The following sections describe the attributes, child elements, and parent elements of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e66cd-110">属性</span><span class="sxs-lookup"><span data-stu-id="e66cd-110">Attributes</span></span>

<span data-ttu-id="e66cd-111">なし。</span><span class="sxs-lookup"><span data-stu-id="e66cd-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e66cd-112">子要素</span><span class="sxs-lookup"><span data-stu-id="e66cd-112">Child Elements</span></span>

<span data-ttu-id="e66cd-113">なし。</span><span class="sxs-lookup"><span data-stu-id="e66cd-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e66cd-114">親要素</span><span class="sxs-lookup"><span data-stu-id="e66cd-114">Parent Elements</span></span>

|<span data-ttu-id="e66cd-115">要素</span><span class="sxs-lookup"><span data-stu-id="e66cd-115">Element</span></span>|<span data-ttu-id="e66cd-116">説明</span><span class="sxs-lookup"><span data-stu-id="e66cd-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e66cd-117">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e66cd-117">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="e66cd-118">Windows PowerShell がオブジェクトの新しいグループを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="e66cd-118">Defines how Windows PowerShell displays a new group of objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e66cd-119">テキスト値</span><span class="sxs-lookup"><span data-stu-id="e66cd-119">Text Value</span></span>

<span data-ttu-id="e66cd-120">新しいグループの表示に使用されるカスタムコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e66cd-120">Specify the name of the custom control that is used to display a new group.</span></span>

## <a name="remarks"></a><span data-ttu-id="e66cd-121">解説</span><span class="sxs-lookup"><span data-stu-id="e66cd-121">Remarks</span></span>

<span data-ttu-id="e66cd-122">書式設定ファイルのすべてのビューで使用できるコモンコントロールを作成できます。また、特定のビューで使用できるビューコントロールを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e66cd-122">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="e66cd-123">次の要素は、これらのカスタムコントロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e66cd-123">The following elements specify the names of these custom controls:</span></span>

- [<span data-ttu-id="e66cd-124">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e66cd-124">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="e66cd-125">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e66cd-125">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="e66cd-126">参照</span><span class="sxs-lookup"><span data-stu-id="e66cd-126">See Also</span></span>

[<span data-ttu-id="e66cd-127">View の GroupBy 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e66cd-127">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="e66cd-128">Configuration の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e66cd-128">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="e66cd-129">View の Controls の Control の Name 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="e66cd-129">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="e66cd-130">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="e66cd-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
